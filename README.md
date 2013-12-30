FileStreamWebApiDemo
====================

This is a simpler version of 
https://github.com/bjartwolf/SqlFileStreamWebApiDemo

It is using a filestream directly instead of SQL Server FILESTREAM.
This is less enterprisy but it can be run without SQL Server and the extra configuration required to run the full demo.

It even includes a large XML dataset.

Just clone and run in Visual Studio.

# Architecture


          +-----------------+
          |                 |
          |     Browser     |
          |                 |
          |  Unpacking gzip |
          +--------+--------+
                   | Content-Encoding: gzip
                   | Content-Type: application/xml
          +--------+--------+
          |                 |
          |    Web API      | Web API serving a binary stream
          |                 | directly from file
          +--------+--------+ 
                   |
          +--------+--------+
          |                 |
          |    Filesystem   | Compressed file stored on disk 
          |                 | 
          +-----------------+
