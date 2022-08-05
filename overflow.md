# overflow



## scroll

- auto나 scroll을 쓸 때는, 속성을 먹인 요소에는 반드시 높이가 지정되거나 white-space가 nowrap으로 지정되어 있어야 하며, 그 조상 요소의 높이에도 주의해야 한다.
  
  - 문제가 발생했던 경우를 예를 들어보자.
  
  - div(grand) > div(parent:overflow) > div(child) 구조에서, 
    
    - grand div의 position이 static이고 높이가 지정되어 있지 않았던 상태 (아무 속성 지정 X & 높이는 내용물에 따름) 
    
    - parent div의 높이를 상위 요소의 %로 지정 
    
    - 그 상태로 child의 개수를 늘려 scroll을 만들려고 했더니, 내용물의 부피를 따르는 grand div는 계속 팽창하고, parent div는 grand를 따라서 높이가 %로 팽창 하여, 결국에는 scroll이 만들어지지 않는 일이 발생했다.

## auto

## hidden

- overflow를 먹인 div를 기준으로, 그 div를 넘어가는 요소들은 사라진다.

- overflow를 먹인상위 요소 는 position이 static이 아닌 value로 지정한다.
  
  - 하위 요소를 상위 요소 기준으로 쌓아야 하기 때문이다.

- 하위 요소는 여러개를 쌓을 거면 relative, 하나를 쌓고 그 내부 요소들에 적용하는 식으로 간다면 absolute로 간다.
