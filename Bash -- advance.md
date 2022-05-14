# Bash -- advance

[TOC]

## commands

### declare

```bash
declare [+/-][rxi][var_name=value] or declare -f
```

- `+/-`：cancel/set var properties
- `r`：read-only
- `f`：print function definition
- `x`:  environmental var
- `i`:  integer
- `a`:  array

### export

```bash
export [-fnp][var_name]=[value]
```

- `f`:  var_name is a function
- `n`:  delete var (not printed afterwards)
- `p`:  list all environment vars

## expansions

### brace expansion {}

- used to generate strings
- ".." will be expanded to continuous chars

### parameter expansion ${parameter}

- ${parameter:-default} :  default value for var

```bash
line=${1:-10}
col=${2:-10}
```

- ${#parameter} :  length of parameter
- ${parameter#pattern} :  match pattern in parameter, return shortest match

### aithmetic expansion

- symbol: $(())

### command substitution

- $(command) or \`command`

## regex

### differences

https://breezetemple.github.io/2019/12/27/regular-expression

## references

1. https://www.cnblogs.com/welkinwalker/archive/2013/02/12/2910288.html
2. https://juejin.cn/post/6844904168738521102