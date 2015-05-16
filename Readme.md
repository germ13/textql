# TextQL

Allows you to easily execute SQL against structured text like CSV or TSV.

Example session:
![textql_usage_session](https://raw.github.com/dinedal/textql/master/textql_usage.gif)

## Major changes!

Since there has been some time since the initial release of textql, I've made some improvements as well as made the project much more modular. There's also been a additional performance tweaks and added functionality, but this comes at the cost of breaking the original command line flags and changing the install command.

## Key differences between textql and sqlite importing

- sqlite import will not accept stdin, breaking unix pipes. textql will happily do so.
- textql supports quote escaped delimiters, sqlite does not.
- textql leverages the sqlite in memory database feature as much as possible and only touches disk if asked.

## Is it any good?

[Yes](https://news.ycombinator.com/item?id=3067434)

## Requirements

- Go

## Install

You may need to `export CC=clang` on OS X.

```bash
go get -u github.com/dinedal/textql/...
```

## Usage

```bash
  -console=false: After all commands are run, open sqlite3 console with this data
  -dlm=",": Delimiter between fields -dlm=tab for tab, -dlm=0x## to specify a character code in hex
  -header=false: Treat file as having the first row as a header row
  -outputHeader=false: Display column names in output
  -save-to="": If set, sqlite3 db is left on disk at this path
  -source="stdin": Source file to load, or defaults to stdin
  -sql="": SQL Command(s) to run on the data
  -table-name="tbl": Override the default table name (tbl)
  -verbose=false: Enable verbose logging
```


## License

New MIT License - Copyright (c) 2014, 2015 Paul Bergeron

See LICENSE for details
