# makepkg.conf
Универсальная сборка пакетов для Arch Linux с агрессивными флагами оптимизации без флагов на безопасность.

# Функционал:
- Профиль clang+openmp+polly+lld
- Профиль clang+openmp+lld
- Профиль clang+lld
- Профиль gcc+openmp+ld
- Профиль gcc+ld

# Установка:
```sudo cp makepkg.conf /etc/makepkg.conf```

# Использование:
1. Если хотите использовать clang или gcc, вам понадобится открыть консоль и экспортировать один из профилей:

```export USE_LLVM=clang``` 
```export USE_GCC=gcc```

2. Дальше вы можете использовать один из профилей на выбор clang или gcc:

```export polly```  - использование clang+openmp+lld+polly

```export clang``` - использование clang+openmp+lld

```export clang-stable``` - использование clang+lld

```export gcc``` - использование gcc+openmp+ld

```export gcc-stable``` - использование gcc+ld

3. Соответственно вы можете собирать пакет для Arch Linux:

```makepkg -sric```
