# Test

## Задача
Написать программу, реализующую алгоритм склейки перелетов. 
Входные данные брать из файла input.json, результат должен помещаться в файл output.json. 
Программа должна быть реализована на Java.
## Описание
На входе дано перечисление строк. Каждая строка состоит из опциональных строковых элементов. ("a1" - элемент присутствует, null- элемент отсутствует) 

[

      [ "a1", "a2", "a3", "a4" ], <- первая строка 

      [ "b1", null, null, "b4" ], 

      [ null, "c2", "c3", null ], <- 3я строка 

      [ "d1", null, null, "d4" ], 

      [ null, "e2", "e3", null ], <- 5я строка 

      [ null, "f2", "f3", "f4" ], 

      [ "h1", null , null, null ], <- 7я строка 

      [ "g1", null , null, null ] 
      
] 

Необходимо получить все возможные сочетания строк так, чтобы их строковые элементы полностью дополняли друг друга. 
## Пример
Полностью дополняющие друг друга строки:

[ 

    [ "b1", null, null, "b4" ], 

    [ null, "c2", "c3", null ] 
  
] 

Ненулевые элементы в одинаковых позициях не могут комбинироваться друг с другом. 
d4 и f4 не могут дополнить друг друга:

[ 

    [ "d1", null, null, "d4" ], 

    [ null, "f2", "f3", "f4" ] 
  
] 

Результат не должен включать в себя неполностью скомбинирование строки. 
Последние элементы null в одной позиции:

[ null, "e2", "e3", null ], 

[ "h1", null , null, null ] 

Результат: 

[ 

    [ "g1", "f2", "f3", "f4" ], <- комбинация 8й и 6й строки
    
    [ "h1", "f2", "f3", "f4" ], <- комбинация 7й и 6й строки 
    
    [ "d1", "e2", "e3", "d4" ], <- комбинация 4й и 5й строки 
    
    [ "d1", "c2", "c3", "d4" ], <- комбинация 4й и 3й строки 
    
    [ "b1", "e2", "e3", "b4" ], <- комбинация 2й и 5й строки 
    
    [ "b1", "c2", "c3", "b4" ], <- комбинация 2й и 3й строки 
    
    [ "a1", "a2", "a3", "a4" ] <- первая строка полностью самодостаточна 
  
] 

Комбинироваться может сколько угодно строк. 

[ 

    [ "a1", null, null, null ],
    
    [ null, "b2", null, "b4" ],
    
    [ null, null, "c3", null ] 
  
] 

Результат: 

[ 

    [ "a1", "b2", "c3", "b4" ]
  
]