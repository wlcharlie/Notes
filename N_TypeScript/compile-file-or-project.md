---
title: Compile File or Project
date: 2022-07-10
tags:
  - typescript
  - notes
  - config
  - tsconfig
---

#### Watch Mode
To auto compile the single file with watch mode
```cmd
tsc [fileName] -w
```

#### Compile Entire Project
Initialize the ts config
```cmd
tsc --init
```

will generate `tsconfig.json` , ref: [more about tsconfig](https://aka.ms/tsconfig.json)

next, to compile all ts file in project with
```shell
tsc

%%or%%

tsc -w
```

#### Igonre Specific File to Compile with Exclude

Using `exclude` in `tsconfig.json`

`**/*` which means any file in any folder

`node_modules` is excluded by default

```json
{
  "compilerOptions": { ... },
  "exclude": ["node_modules", "**/*.d.ts"]
}
```

#### Compile Specific with Include
##### Include
Using `include` in `tsconfig.json`

process are like: `include - exclude` 

**if the `include` exitsed, it will only compile that was provided**

##### Files
point to specific **files**

```json
{
  "compilerOptions": { ... },
  "include": [...]
  "files": [...]
}
```

