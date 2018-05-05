# rb_tree@0.0.1

### Задание
Написать программу для работы с красно-черным деревом:
- `+` - добавить ключ
- `?` - найти ключ
- `=` - вывести на экран дерево
- `q` - выйти

### Замечания
Для реализации красно-черного дерева используйте класс следующего вида:
```
class rb_tree_t
{
private:
    enum class color_t {
      black,
      red
    };
    struct node_t {
        node_t * left;
        node_t * right;
        node_t * parent;
        color_t color;
        int key;
    };
private:
    node_t * root_;
public:
    void insert(int key);
    bool find(int key) const;
    void print(std::ostream & stream) const;
};
```

### Входные данные
Во входных данных заданы строки, следующего формата:
```
+ <число>
? <число>
=
q
```

### Примеры
```
+ 2
----b2

+ 1
----b2
--------r1

+ 3
--------r3
----b2
--------r1
? 1
true

? 4
false

=
--------r3
----b2
--------r1

q
```

# rb_tree@0.0.2

### Задание
- Сделать класс шаблоном
- Добавить метод удаления ключа
- Добавить метод сравнения деревьев
- Добавить поддержку списка инициализации
- Реализуйте тесты ко всем открытым методам класса

### Замечания
Для реализации бинарного дерева поиска используйте класс следующего вида:
```
template <typename T>
class rb_tree_t
{
private:
    enum class color_t {
      black,
      red
    };
    struct node_t {
        node_t * left;
        node_t * right;
        node_t * parent;
        color_t color;
        T key;
    };
public:
    tree_t(std::initializer_list<T> keys);
    auto operator==(tree_t const & other) const;
    void insert(T key);
    bool remove(T key);
    bool find(T key) const;
    void print(std::ostream & stream) const;
};
```
