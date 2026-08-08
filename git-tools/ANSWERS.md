# Домашнее задание "Инструменты Git"
 
Репозиторий для анализа: https://github.com/hashicorp/terraform 
 
## 1. Полный хеш и комментарий коммита, начинающегося на aefea
 
Команда:
```
git log --all --oneline | grep aefea
git rev-parse aefead2207
```
 
Ответ:
- Хеш: `aefead2207ef7e2aa5dc81a34aedf0cad4c32545`
- Комментарий: `Update CHANGELOG.md`
 
## 2. Тег коммита 85024d3
 
Команда:
```
git tag --points-at 85024d3
```
 
Ответ: `v0.12.23`
 
## 3. Сколько родителей у коммита b8d720
 
Команда:
```
git show -s --format="%H%n%P" b8d720
```
 
Ответ: два родителя (merge-коммит):
- `56cd7859e05c36c06b56d013b55a252d0bb7e158`
- `9ea88f22fc6269854151c571162c5bcf958bee2b`
 
## 4. Коммиты между тегами v0.12.23 и v0.12.24
 
Команда:
```
git log v0.12.23..v0.12.24 --oneline
```
 
Ответ:
```
33ff1c03bb v0.12.24
b14b74c493 [Website] vmc provider links
3f235065b9 Update CHANGELOG.md
6ae64e247b registry: Fix panic when server is unreachable
5c619ca1ba website: Remove links to the getting started guide's old location
06275647e2 Update CHANGELOG.md
d5f9411f51 command: Fix bug when using terraform login on Windows
4b6d06cc5d Update CHANGELOG.md
dd01a35078 Update CHANGELOG.md
225466bc3e Cleanup after v0.12.23 release
```
 
## 5. Коммит создания функции func providerSource(...)
 
Команда (pickaxe-поиск по добавлению/удалению строки):
```
git log -S "func providerSource(" --oneline -- '*.go'
```
 
Найден один коммит, проверено через git show, что функция добавлена (все строки с +):
```
git show 8c928e8358 -- '*.go' | grep -B2 -A5 "func providerSource"
```
 
Ответ: `8c928e8358` - "main: Consult local directories as potential mirrors of providers"
 
## 6. Все коммиты, изменявшие функцию globalPluginDirs
 
Команда (поиск по изменению строки в diff):
```
git log -G "globalPluginDirs" --oneline -- '*.go'
```
 
Ответ:
```
7c4aeac5f3 stacks: load credentials from config file on startup (#35952)
22a2580e93 main: Use the new cliconfig package credentials source
35a058fb3d main: configure credentials from the CLI config file
c0b1761096 prevent log output during init
8364383c35 Push plugin discovery down into command package
```
 
## 7. Автор функции synchronizedWriters
 
Команда:
```
git log -S "func synchronizedWriters" --oneline -- '*.go'
```
 
Найдено два коммита, проверено через git show, какой из них создаёт функцию:
```
git show 5ac311e2a9 -- '*.go' | grep -B2 -A5 "func synchronizedWriters"
```
 
Коммит `5ac311e2a9` ("main: synchronize writes to VT100-faker on Windows") добавляет функцию (все строки с +).
 
Команда для получения автора:
```
git show -s --format="%an <%ae>" 5ac311e2a9
```
 
Ответ: Martin Atkins <mart@degeneration.co.uk>
