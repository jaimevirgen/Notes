# Notes
A small terminal utility for taking notes.

Version 0.1

## What is this repository for?
This is a small utility that can be
added to your bash profile to take notes in.

## How do I get set up?

### Homebrew
   * Dependencies
   * [AG](https://github.com/ggreer/the_silver_searcher) improves upon ack

```
   brew install the_silver_searcher
```

### Add Notes directory
   * Notes Dir

```
   mkdir path/to/Notes
```

### Add alias to .bash_profile in root directory
   what is a [bash profile?](https://apple.stackexchange.com/questions/99835/how-to-create-bash-profile-and-profile)
   
   Add the following lines to your ~/.bash_profile
```
alias notes='touch path/to/Notes/$(date '+%Y%m%d').txt; vim + path/to/Notes/$(date '+%Y%m%d').txt'
ask () { ag -i -A --column "$@" path/to/Notes; }
```


## How do I use Notes?

### run Notes from Anywhere
```
   notes
```

   that's it!
   
   This will open vim into today's notes entry, if already opened will append to end of file.

### search through Notes
   This will return a list of all the entries that contain 'keyword'.
   
   Keep in mind this is case sensitive.

```
   ask keyword
```
   
   To only return 3 matches and ignore case modify your alias to

```
   ask () { ag -i -A --column --max-count 3 --ignore-case "$@" path/to/Notes; }
```


## Development Notes

#0.1
* Adding alias commands to Readme
