# Level 2

## Objetivo
- Read the "spaces in this filename" file, which is in the current directory (home) to get the next level password.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit2
- Password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

## Solución
- Read the file using "cat 'spaces in this filename' " or "cat spaces\ in\ this\ filename".


## Notas adicionales
If you want to work with files that have spaces in their name, you have to use single quotes in the filename. Otherwise, you can also use "\" after each word. You can use "cat", then tab to autocomplete the name.