+++
date = '2025-01-23T12:19:39+03:00'
draft = false
title = 'ኒዮቪም ተርመክስ ላይ ስለመጫን'
tags = ["termux", "intro", "linux-tools", "amharic"]
categories = ["termux-tutorial", "neovim-tutorial"] 
+++
`{{< viewcount >}}`


ኒዮቪምን ተርመክስ ላይ ለመጫን ሁለት መንገዶች አሉ። ከተርመክስ የፕሮግራም ቋት ማውረድ እንችላለን። የተርመክስ ተርኒናላችን ላይ `pkg i neovim` የሚለውን ኮማንድ በመጠቀም።

በተጨማሪም የኒዮቪምን ሶርስ ኮደ ከጊትሃብ በማውረድ እና በማቀናበር (compile) በማድረግ አዲስ የሆነዉኑ ባህሪያትን (features) ማግኘት እንችላለን። ለተርመክስ እና ለኒዮቪም አዲስ ከሆነን ከተርመክስ ረፖዚቶሪ (ቋት) በማውረድ በንጠቀም ከበቂ በላይ ነው። ከሶርስ በማውረድ እና ኮምፓይል በማደረግ ለመጠቀም ክቅዚህ በታች ያሉትን ኮማዶች መጠቀም እንችላለን።


### አስፈላጊ ፕሮግራሞች

ኮምፓይል ከማድረጋችን በፊት አስፈላጊ ነገሮችን ማውረድ እና ሲስተማችን ላይ መጫን ያስፈልገናል። ለምሳሌ `git` ሪፖዚቶሪ ክሎን ለማድረግ፣ `cmake` ኮምፓይል ለማድረግ እናሌሎች ፕሮግራሞችን መጫን ያስፈልጋል። 

```bash
# አስፈላጊ ፕሮግራሞችን ለመጫን
pkg install git ninja gettext cmake curl build-essential luajit lua51-lpeg tree-sitter libtool automake utf8proc lua51 libluajit luarocks
```


### ቋቱን ወደ ሲስተማችን ለመቅዳት (clone the repository)
 
 ሙሉ የ ነዮቪም ቋትን አውርደን መጠቀ ብንችልም፤ ቀጥሎ ያልው የ ጊት ኮማንድ የምንፈልገውን ብራንች "nightly" እና የመጨረሻ ኮፒ 'depth=1' የቀዳልናል።
 
```bash
#ቋቱን ለመቅዳት
git clone https://github.com/neovim/neovim --branch nightly --depth=1
```
### ማቀናበር (compiling)

```bash
cd neovim # ክሎን ወዳደረነው ዳይሬክተሪ ለመግባት
mkdir build # 'build' የሚል ዳይሬክተሪ ለመፍጠር
cd build # ወደ 'build' ዳይሬክተሪ ለመግባት
cmake -DCMAKE_INSTALL_PREFIX=$HOME/.local .. # ኮምፓይል ለማድረግ
make install # ኮምፓይል ያደረኘውን ለመጫን
```

### ከጫንን በኋላ

የሲስተማችን  `$PATH` ቫርያብለ የሚከተልውን የፋይል አድራሻ `~/.local/bin` መያዝ አለበት
ቀጥሎ ያለዉን ኮድ `~/.zshrc` ወይንም `~/.bashrc` ዉስጥ ጨምሩ

 `export PATH=$HOME/bin:$HOME/.local/bin:/usr/local/bin:$PATH`

> ካስቸገራችሁ ጻፉልኝ

ቻውቻው
