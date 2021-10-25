# `grep` Cheatsheet

- Get the PDF version [`here`](https://github.com/aafulei/grep/raw/main/grep-cheatsheet.pdf)

## Synopsis

```
grep [OPTION...] PATTERNS [FILE...]
```

## Sample File

- [`sample.txt`](./sample.txt)

```
[ID]    [Name]      [Position]      [Division]      [Salary]
 10      Alice       Manager         Sales           $8,000
 20      Bob         Developer       Technology      $7,000
 30      Charlie     Specialist      Technology      $5,000
 40      David       Manager         Marketing       $9,000
 50      Eva         Specialist      Sales           $4,000
 60      Evan        Developer       Technology      $6,000
```

## Show Context

```sh
# -1 is equivalent to --context=1
grep -1 David sample.txt
grep -C 1 David sample.txt
grep --context=1 David sample.txt
```

## Show Line Number

```sh
grep -n Manager sample.txt
grep --line-number Manager sample.txt
```

## Logical OR

```sh
grep "Sales\|Marketing" sample.txt
grep -e Sales -e Marketing sample.txt
grep -regexp Sales --regexp Marketing sample.txt
```

## Logical AND

```sh
grep Manager sample.txt | grep Sales
```

## Logical NOT

```sh
grep -v Manager sample.txt
grep --invert-match Manager sample.txt
```

## Ignore Case

```sh
grep -i manager sample.txt
grep --ignore-case manager sample.txt
```

## Whole Word

```sh
grep "\bEva\b" sample.txt
```

## No Regular Expression

```sh
grep -F "[ID]" sample.txt
grep --fixed-strings "[ID]" sample.txt
```
