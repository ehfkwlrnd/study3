# pandas 학습

* 초기값

  ```python
  df = pd.DataFrame([1, 2, 3])
  '''
     0
  0  1
  1  2
  2  3
  '''
  
  df = pd.DataFrame([[1, 2, 3], [4, 5, 6]])
  '''
     0  1  2
  0  1  2  3
  1  4  5  6
  '''
  
  df = pd.DataFrame(data=[[1, 2], [3, 4]], columns=['A', 'B'])
  '''
     A  B
  0  1  2
  1  3  4
  '''
  
  data = {
      'year' : [2016, 2017, 2018],
      'GDP rate' : [2.8, 3.1, 3.0],
      'GDP' : ['1.637M', '1.7M', '1.83M']
  }
  df = pd.DataFrame(data)
  '''
     year  GDP rate     GDP
  0  2016       2.8  1.637M
  1  2017       3.1    1.7M
  2  2018       3.0   1.83M
  '''
  ```

* update value

  ```python
  data = {
      'year' : [2016, 2017, 2018],
      'GDP rate' : [2.8, 3.1, 3.0],
      'GDP' : ['1.637M', '1.7M', '1.83M']
  }
  df = pd.DataFrame(data)
  df.iloc[0, df.column.get_loc('year')] = 2011
  print(df)
  '''
     year  GDP rate     GDP
  0  2011       2.8  1.637M
  1  2017       3.1    1.7M
  2  2018       3.0   1.83M
  '''
  ```

* update

  ```python
  data = {
      'year' : [2016, 2017, 2018],
      'GDP rate' : [2.8, 3.1, 3.0],
      'GDP' : ['1.637M', '1.7M', '1.83M']
  }
  df = pd.DataFrame(data)
  df.update({'year' : [2011, 2012, 2013]})
  print(df)
  '''
     year  GDP rate     GDP
  0  2011       2.8  1.637M
  1  2012       3.1    1.7M
  2  2013       3.0   1.83M
  '''
  ```

* add value

  ```python
  data = {
      'year' : [2016, 2017, 2018],
      'GDP rate' : [2.8, 3.1, 3.0],
      'GDP' : ['1.637M', '1.7M', '1.83M']
  }
  df = pd.DataFrame(data)
  df.loc[df.index.stop] = {2019, 0, '0M'}
  print(df)
  '''
     year  GDP rate     GDP
  0  2016       2.8  1.637M
  1  2017       3.1    1.7M
  2  2018       3.0   1.83M
  3  2019       0.0      0M
  '''
  ```

* query

  ```python
  data = {
      'year' : [2016, 2017, 2018],
      'GDP rate' : [2.8, 3.1, 3.0],
      'GDP' : ['1.637M', '1.7M', '1.83M']
  }
  df = pd.DataFrame(data)
  
  print(df[df['year'] > 2016][['year','GDP']])
  '''
     year    GDP
  1  2017   1.7M
  2  2018  1.83M
  '''
  ```

  

