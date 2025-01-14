# makepkg.conf
Универсальный makepkg для Arch Linux с агрессивными флагами оптимизации.

# Функционал:
- makepkg.conf - профили без флагов на безопасность
- makepkg-safe.conf - профили с добавлением флагов на безопасность
- Профиль clang+openmp+polly+lld
- Профиль clang+openmp+lld
- Профиль clang+lld
- Профиль gcc+openmp+ld
- Профиль gcc+ld

# Установка:
```sudo cp makepkg.conf /etc/makepkg.conf``` - перезапишется ваш стандартный makepkg.conf, но вы можете переместить makepkg.conf в любое удобное вам место.

# Использование:

1. Установка зависимостей для clang и gcc:

```sudo pacman -S llvm clang lld openmp polly```

2. Если хотите использовать clang или gcc, вам нужно экспортировать один из профилей:

```export USE_LLVM=clang```
 
```export USE_GCC=gcc```

3. Дальше вы можете использовать один из профилей на выбор clang или gcc:

```export PROFILE=clang-polly```  - использование clang+openmp+lld+polly

```export PROFILE=clang``` - использование clang+openmp+lld

```export PROFILE=clang-stable``` - использование clang+lld с менее агрессивными флагами

```export PROFILE=gcc``` - использование gcc+openmp+ld

```export PROFILE=gcc-stable``` - использование gcc+ld с менее агрессивными флагами

4. Соответственно вы можете собирать пакет для Arch Linux:

```makepkg -sric```

```makepkg -sric --config /путь/makepkg.conf``` - если вы переместили makepkg.conf в другое место, то укажите путь к нему

Если у вас будут какие-то проблемы при сборке на clang, пожалуйста, не пишите мне об этом. Но если имеются проблемы при сборке на gcc или возникли какие-то проблемы при использовании(или регрессии в производительности), то напишите об этом в issue или в Telegram: https://t.me/Terromur 

Так же приветствуются предложения по добавлению флагов на ещё большую оптимизацию, но не приветствую по добавлению флагов на безопасность.

Так же из моих наработок для сборки с агрессивной оптимизацией: https://github.com/Terromur/PKGBUILDs
