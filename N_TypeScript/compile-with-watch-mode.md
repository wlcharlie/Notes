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

