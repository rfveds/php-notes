# PHP File System Basics

## Listing Files/Directories
- `scandir($path)` lists files and directories in given path
  - Returns array: `.` (current dir), `..` (parent dir), file/directory names
  - Use `is_file()` and `is_dir()` to check if item is file or directory

## Creating/Deleting Directories  
- `mkdir($dirname, $permissions, $recursive)` creates directory
  - Permissions default 0777, recursive default false
- `rmdir($dirname)` deletes directory (must be empty)
  - Recursive delete requires custom function

## Checking File/Directory Existence
- `file_exists($filename)` checks if file or directory exists
- Be aware PHP caches results of some file functions like `filesize()` 
  - Clear cache with `clearstatcache()`

## Opening/Reading Files
- `fopen($filename, $mode)` opens file and returns resource 
  - Modes: 'r' (read), 'w' (write), 'a' (append), etc.
  - Can open remote files via URL if enabled
  - Returns false on failure, use `file_exists()` to check first
- `fgets($resource)` reads line from file, returns false at EOF
  - Loop and echo to read file line-by-line
- `fgetcsv($resource, $length, $delimiter)` parses CSV line into array
  - Default delimiter is comma
- `file_get_contents($filename, $use_include_path, $context, $offset, $length)` reads entire file into string
  - Can specify offset and length to read portion of file
- Always `fclose($resource)` when done

## Writing Files  
- `fwrite($resource, $string)` writes to file
- `file_put_contents($filename, $data, $flags)` writes entire file  
  - Creates file if doesn't exist, otherwise overwrites
  - Use `FILE_APPEND` flag to append instead of overwrite

## Deleting Files
- `unlink($filename)` deletes file

## Copying/Moving Files
- `copy($source, $dest)` copies file, overwrites if exists
- `rename($oldname, $newname)` moves/renames file or directory  

## Getting File Info
- `pathinfo($path)` returns array with dirname, basename, extension, filename

