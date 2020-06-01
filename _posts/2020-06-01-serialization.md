---
layout: post
title: Serialization Heard 'Round The World
feature-img: "https://images.unsplash.com/photo-1501503069356-3c6b82a17d89"
thumbnail: "https://images.unsplash.com/photo-1501503069356-3c6b82a17d89"
image: "https://images.unsplash.com/photo-1501503069356-3c6b82a17d89" #seo tag
tags: [Data, Serialization]
---

It's easy to bring up the buzzword of 'big data' without having the context of why it's such a big deal and what are the value for info like those — besides seeing green and all. Data collected from some statistics, sensors, or even just an existing database are used by developer to help make it a bit easier to work on tasks or analyst to process and synthesize to understand trends in a quantitative manner, and to people who might just see it from outset are only asking to the higher ups on what is the point of collecting those for and the concerning ethics behind it.

To me, what I want to ask is how does one go about making those data be something that can be easy to look at and process, and for the past year, I am just trying to wrap my head around what developers mean to 'serialize' data and why is it even important to make object attributes be outputted to a text file in a structured manner like CSV, XML, JSON, or YAML or even just compact it all in a binary file out of security sakes.

And with some time fiddling around with how to make sense with reading and writing CSVs and YAML files — sometimes by hand because I'm a masochist, I think it's a valuable tool programmers to understand if they want to get into any development where data has to be retained from one place to another.

So let's not beat around the bush and talk about Data Serialization, the various formats available and the various use cases.

---

* TOC
{:toc}

---

# What is Data Serialization?

In layman's term, **data serialization** is the process of converting structured data — say, an object instance or an ordered array — into a format that can be shared or stored and allowed it to be recovered to its original form. This process is important for sending data through internet, saving it to files, or have it be written in a way that many programs can understand and process from it. And much of the modern serializations formats like JSON and YAML are what many developers use to build applications throughout the internet and reading and writing those formats are readily available in third party packages or even in the included library for almost every programming languages you can think of, so it doesn't hurt to just Google for a parse for a desired format for a desired language and see what you got.

# Serialization Formats

A common thing to consider before picking a format is basically what are you using it for. Do you want it to be readable? Do you want it to be light and portable to transfer? Or do you want it to be secure in a way that it would be difficult to be read or even decrypt without a special key? It is a design decisions much like anything else in software development and serialization is no exception.

## CSV

When you have data that are organized in a table in terms of rows and columns, a *Comma-Separated Values* (**CSV**) files are the most basic but still effective formats that — while not being formally standardized — can make storing files in a more concise manner

At its most basic: each line of the file can be an entry and each values separated by columns (hence the name) are the entry's attributes. Looking at a CSV file below at a glance:

```
John, Doe, john_doe@company.com
Jane, Smith, jane_smith@company.com
Benny, Benson, benny_benson@company.com
```

And you can easily assume that you are looking at a database without much formatting.

```
First | Last   | E-Mail
----- | ------ | ------------------------
John  | Doe    | john_doe@company.com
Jane  | Smith  | jane_smith@company.com
Benny | Benson | benny_benson@company.com
```

There is considerable support for working with CSV with some lookup with Python, in particular, being an included feature with its own [`csv`](https://docs.python.org/3/library/csv.html) module in the standard library.

As I mentioned, this is not a standardized format and that means people might as well easily switch commas with tabs or whatever else that might not be able with everyone else. That being said, it's best to look into those documentation as they can help with some formatting work to make reading a certain CSV more workable.

## XML

*EXtensible Markup Language* (**XML**) is one of the earlier standardized serialization formats that is intended to be read throughout the internet and from the outset, you could be forgiven if you thought you were reading HTML and not XML with how it is written:

```xml
<?xml version="1.0"?>
<employee gender="female">
  <first>John</first>
  <last>Smith</last>
  <email>john.smith@company.com</email>
</employee>
```

Sometimes parsing and serializing XML and HTML are the same and back in my Sophomore year in college, we have to make it XHTML compliant to make it more interoperable and make a more stricter standard for the future of web - which since it's initial standardization by the [World Wide Web Consortium (W3C)](https://www.w3.org/TR/xhtml1/) back at the dawn of the new millennium (January 26th, 2000), it seems to make its use of making web scraping a lot easier thanks to some support with packages like Python's [`lxml`](https://lxml.de/) package to make reading HTML and by extension XML a lot more easier.

And outside out that, XML had been used to serialize RSS and Atom feed, SVG files, and even Office documents starting at Office 2007 with the old `.doc`, `.ppt`, and `.xls` files for Word Documents, PowerPoint Presentations, and Excel Sheets — respective — having the addition of the `x` suffix to be Office Open XML compliant where you can see the deeper XML implementation by changing those files to a `.zip` and looking at its insides from there.

Looking at those however and its clear that it's *way* too verbose to be readable no thanks to the HTML tags and it might as well take in too much file space because of it and there had been criticism of its security, but for more stable file integrity, XML had been running the internet sufficiently in the aughts.

## JSON

The *JavaScript Object Notation* (**JSON**) — first concocted around the turn of the new millennium — was also designed to be a more lightweight and more readable format, and despite being named after one of the most ubiquitous language that is not Python, it doesn't have to be only JavaScript as many languages have [support](https://www.json.org/json-en.html) to read this open standard format with some like Python have JSON support as part of the standard library `json` which reading it as a Pythonista, you would be easily forgiven for reading a Python Dictionary Type:

```json
{
    "Jane Smith": {
        "first": "Jane",
        "last": "Smith",
        "email": "jane_smith@company.com"
    },
    "John Doe": {
        "first": "John",
        "last": "Doe",
        "email": "john_doe@company.com"
    }
}
```

And this is because JSON is structured as a name/value pair — basically a Dictionary or a Hash-Table — but with an ordered set.

This format can be a very easy and very popular way to transfer data from one place to another for millions of others to use in a lightweight packet.

## YAML

One might thing **YAML** is "Yet Another Markup Language," but there are quick to point out that "*YAML Ain't Markup Language*" because this is not a markup language - this is a data-serialization format.

Trashy commentating the obvious aside, YAML allows being even *more* concise with it its Python-style indentation and its key-value advantage being a more concise format with lists either be contained in brackets or brackets. That being said, it's loose nature does make it somewhat hard to follow, but it still can be followable:

```yaml
employee:
- first:  John
  last:   Smith
  e-mail: john_smith@company.com
- first:  Jane
  last:   Doe
  e-mail: jane_doe@xcompany.com
```

And just like JSON, YAML has a lot of [support](https://yaml.org/) in its integration for many modern languages.

## Binary

Technically this is not an actual format, but having your data set in an unreadable binary format allows to be rather secure because of its unreadability outside of the intended program. Attempting to read it, you might as well be prompted to ask for a type or an error or just see a hex dump on your text editor.

The only support to create serializable binary data is in C# with allowing support for any format including binary under `System.Runtime.Serialization.Formatter.Binary` (yeah that is long), so if you are using C#, you're lucky, especially for Unity developers for save and load files. Other than that, you are on your own trying to write down a binary file for any other languages.

# Use Cases

All of those formats as I listed above have their uses and their limitations but all of those have their place.

## File Read and Write

Any file — whether if its documents or save files for games — have utilized serialization so it would be pulled up and held its current state or information when the user needs to resume at a later time. XML had been the go-to solution for saving files from SVGs and word docs (replace s to x) for the early internet and even now as a means of making files secure from error by corruption. But if it's for more protection from user tempering, binary files can do it.

## Class Object Representation

For when you need to store or grab data from a local database or in any sort of list, a CSV or JSON can do the work as the structure can make it easy to reconstruct in a database (either in SQL engines or any other languages) where reproducibility and consistency is an important factor.

## REST API

A *REpresentation State Transfer* (**REST**) API as a web-service interface makes getting a certain set of data from a server simple as a means of interacting with it as straightforward as possible with a request to it. One of the common output for getting data in a REST API is JSON, and the concerns of security are subsided thanks to reading and writing is by an authenticity basis like [Oauth](https://oauth.net/2/) and the JSON output from a GET request is the result of parsing through a read-only query through a Database.

# Conclusion

Data Serialization is an open-ended integration that can only be done right if you understand the benefits and limitations of what formats you are using. Now you get an understanding of what serialization can do to record or send data through the web.

Happy coding.
