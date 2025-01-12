# makepkg.conf
Универсальная сборка пакетов для Arch Linux с агрессивными флагами оптимизации без флагов на безопасность.

# Функционал:
- Профиль clang+openmp+polly+lld
- Профиль clang+openmp+lld
- Профиль clang+lld
- Профиль gcc+openmp+ld
- Профиль gcc+ld

# Установка:
```sudo cp makepkg.conf /etc/makepkg.conf``` - перезапишется ваш стандартный makepkg.conf, но вы можете переместить makepkg.conf в любое удобное вам место.

# Использование:
1. Если хотите использовать clang или gcc, вам понадобится открыть консоль и экспортировать один из профилей:

```export USE_LLVM=clang```
 
```export USE_GCC=gcc```

2. Дальше вы можете использовать один из профилей на выбор clang или gcc:

```export PROFILE=polly```  - использование clang+openmp+lld+polly

```export PROFILE=clang``` - использование clang+openmp+lld

```export PROFILE=clang-stable``` - использование clang+lld

```export PROFILE=gcc``` - использование gcc+openmp+ld

```export PROFILE=gcc-stable``` - использование gcc+ld

3. Соответственно вы можете собирать пакет для Arch Linux:

```makepkg -sric```

```makepkg -sric --config /makepkg.conf``` - если вы переместили makepkg.conf в другое место, то укажите путь к нему

Если у вас будут какие-то проблемы при сборке на clang, пожалуйста, не пишите мне об этом. Но если имеются проблемы при сборке на gcc или возникли какие-то проблемы при использовании, то напишите об этом в issue или в Telegram: https://t.me/Terromur 

Так же привествуется предложение по добавлению флагов на ещё большую оптимизацию, но не приветствую по добавлению флагов на безопасность. Возможно в будущем добавлю отдельный makepkg.conf для этого.
