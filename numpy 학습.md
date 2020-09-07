# numpy 학습

* 배열 초기값

  ```python
  import numpy as np
  
  a = np.array([
      [1, 2, 3],
      [4, 5, 6]
  ])
  
  b = np.zeros((2, 3), dtype=int)
  
  c = np.ones((2, 3), dtype=int)
  
  d = np.eye(2, dtype=int)
  
  e = np.full((2, 3), 5)
  #5로 가득찬 배열
  
  f = np.arange(1, 7)
  #start, stop, int
  
  g = np.arange(0, 1, 0.1, dtype=float)
  #start, stop, step, float
  
  h = np.random.randint(0, 10, (2, 3))
  ```

* 배열 계산

  ```python
  import numpy as np
  
  a = np.array([
      [1, 2, 3],
      [4, 5, 6]
  ])
  
  b = 2 * a #각 원소에 2를 곱함
  c = 2 + a #각 원소에 2를 더함
  
  d = a * a #각 원소별로 곱함
  e = a + a #각 원소별로 더함
  
  x = np.array([
      [1],
      [1],
      [1]
  ])
  
  f = np.dot(a, x) #내적
  '''
  [
      [6], 
  	[15]
  ]
  '''
  ```

* 집계 연산

  ```python
  import numpy as np
  
  a = np.array([
      [1, 2, 3],
      [4, 5, 6]
  ])
  
  #axis=0 column
  #axis=1 row
  b = np.sum(a, axis=0) #[5, 7, 9]
  b = np.sum(a, axis=1) #[6, 15]
  
  c = np.prod(a, axis=0) #[4, 10, 18]
  c = np.prod(a, axis=1) #[6, 120]
  
  d = np.mean(a, axis=0)
  d = np.mean(a, axis=1)
  ```

* 슬라이싱

  ```python
  import numpy as np
  
  a = np.array([
      [1, 2, 3],
      [4, 5, 6]
  ])
  
  b = a[0, 0] #1
  c = a[0, [0, 2]] #[1, 3]
  d = a[0, :] #[1, 2, 3]
  e = a[:, [0, 2]] #[[1, 3], [4, 6]]
  f = a[[0,1], [0, 2]] #[1, 6]
  g = a[:, 1:] #[[2, 3], [5, 6]]
  
  bool_index = [
      [True, False, False],
      [True, False, False]
  ]
  
  h = a[bool_index] #[1, 4]
  l = a[a%2 == 0] #[2, 4, 6]
  ```

* 속성

  ```python
  import numpy as np
  
  a = np.array([
      [1, 2, 3],
      [4, 5, 6]
  ])
  
  a.ndim #2 (1차원 배열인지, 2차원 배열인지)
  a.shape #(2, 3)
  a.size #6
  a.dtype #int32
  ```

* reshape

  ```python
  import numpy as np
  
  a = np.array([
      [1, 2, 3],
      [4, 5, 6]
  ]).reshape((3, 2))
  '''
  [
  	[1, 2],
      [3, 4],
      [5, 6]
  ]
  '''
  
  a = np.arange(1, 5, dtype=int).reshape((2, 2))
  '''
  [
      [1, 2],
      [3, 4]
  ]
  '''
  ```

* split

  ```python
  import numpy as np
  
  a = np.arange(0, 10) #[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
  b = np.split(a, [2, 4]) #[[0, 1], [2, 3], [4, 5, 6, 7, 8, 9]]
  ```

  

