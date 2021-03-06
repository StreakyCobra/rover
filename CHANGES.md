# Change Log

## [0.4.1] - 2016-01-03

### New Features

- Add `--save-marks` option to save pathname of marked entries upon exit.
- Add option to use a shell to launch external programs more flexibly.
  - e.g. `PAGER="less 2> /dev/null -N" rover`

### Bug Fixes

- Fix file operations on symbolic links.
  - Don't dereference symlinks when copying.
  - Don't dereference symlinks to directories during batch operations.
- Fix build error on platforms that disable SIGWINCH in the name of POSIX.

## [0.4.0] - 2015-08-21

### Important changes in default configuration

- The key for "delete selected file or (empty) directory" is now 'D'.
  - The old key ('x') was too similar to "delete all marked entries" ('X').
- The keys for "refresh listing" & "rename" were swapped to 'r' & 'R', resp.
  - This is more consistent, keeping file operations on uppercase keys.

### New Features

- Considerably improved status messages.
  - "Moving..." (or similar) instead of "Processing...".
  - ""foo.txt" already exists" (or similar) instead if "File already exists.".
- Show progress during batch processing (e.g. "Moving...63%").
- Update directory listing as it is affected by batch operations.
- Add optional alert to inform that a batch operation has finished.
- Support color customization of other kinds of files.
  - Each file type described in stat(2) can now have its own color.
  - Executable files can also have their own color.

### Bug Fixes

- Check if directory is accessible before changing the current path.
- Fix crash on long path names.
- Show long status messages partially, instead of nothing at all.
- Fix some scrollbar-related issues.

## [0.3.0] - 2015-06-21

### New Features

- Unicode support.
- New commands 'g' & 'G' to jump to top & bottom of listing.
- New option `--save-cwd` to save last visited path to a file before exiting.
- New helper script `rover.sh` to use Rover as "interactive cd".

### Bug Fixes

- Handle symbolic links to directories as such, rather than regular files.
- Add missing make target for uninstalling Rover.
- Fix unsafe behavior on terminal resizing.

## [0.2.0] - 2015-06-03

### New Features

- Better line editing (for search, rename, etc):
  - Allow cursor movement, insertion and deletion.
  - Horizontal scrolling for long lines in small terminals.
- New command 'R' to refresh directory listing.
- New command 'x' to delete selected file or (empty) directory.
- Show file sizes in human readable format ("1.4 K" instead of "1394").
- Set environment variable $RVSEL to selection before running a subprocess.

## [0.1.1] - 2015-04-17

### Bug Fixes

- Fix flashing on slow terminals.
- Fix crash on terminal resizing during subprocess execution.
- Accept relative paths as arguments.
- Don't overwrite default background color.
- When listing symbolic links, show link size instead of target size.
- Remove possible buffer overflows.

## [0.1.0] - 2015-03-07

First version.
