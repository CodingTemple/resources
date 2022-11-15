# Useful Changes in Python 3.9


### Updating a Dictionary



``` python
import sys
# checking your python version
print(f"Your python version is {sys.version_info.major}.{sys.version_info.minor}")
```

> Your python version is 3.9





### Use Python 3.9+

To use features in python 3.9 in jupyter notebook (if its not already
your default version):

Check the code above and if it outputs a version lower that 3.9 you will
need to stop your jupyter notebook server <br> then in the
terminal/command line run: <code> conda create --name python39
python==3.9 conda activate python39 conda install jupyter notebook
jupyter notebook </code>


``` python
nfl_mvp_15_17={
    2015:"Cam Newton",
    2016:"Matt Ryan",
    2017:"Tom Brady",

}
nfl_mvp_18_20={
    
    2018:"Patrick Mahomes",
    2019:"Lamar Jackson",
    2020:"Aaron Rodgers"
}
```


### We can now unpack our dictionaries using **

``` python
#unpacking method
{**nfl_mvp_15_17, **nfl_mvp_18_20}
```



>    {2015: 'Cam Newton',
>     2016: 'Matt Ryan',
>     2017: 'Tom Brady',
>     2018: 'Patrick Mahomes',
>     2019: 'Lamar Jackson',
>     2020: 'Aaron Rodgers'}





``` python
#looping method
nfl_mvps = nfl_mvp_15_17.copy()
for key, value in nfl_mvp_18_20.items():
    nfl_mvps[key] = value
print(nfl_mvps)
```



>    {2015: 'Cam Newton', 2016: 'Matt Ryan', 2017: 'Tom Brady', 2018: 'Patrick Mahomes', 2019: 'Lamar Jackson', 2020: 'Aaron Rodgers'}


``` python
#inplace method with update
print(type(nfl_mvp_15_17.update(nfl_mvp_18_20))) #return type of None

print(nfl_mvp_15_17)
```
>    {2015: 'Cam Newton', 2016: 'Matt Ryan', 2017: 'Tom Brady', 2018: 'Patrick Mahomes', 2019: 'Lamar Jackson', 2020: 'Aaron Rodgers'}





## New in Python 3.9

You can update dictionaries in place with the in-place union operator (
|= )<br> or out of place with the union operator ( | )<br> works with
dictionary like data type (like default dict)<br> Note: In all the cases
in this worksheet if a key is duplicated in both dictionaries the value
of the second dictionary will take that key, so in these examples
nfl\_mvp\_18\_20 identical key will override nfl\_mvp\_15\_17 value



``` python
#Out of Place
nfl_mvps=nfl_mvp_15_17 | nfl_mvp_18_20
print(nfl_mvps)
```



>    {2015: 'Cam Newton', 2016: 'Matt Ryan', 2017: 'Tom Brady', 2018: 'Patrick Mahomes', 2019: 'Lamar Jackson', 2020: 'Aaron Rodgers'}



``` python
#In place
nfl_mvp_15_17 |= nfl_mvp_18_20
print(nfl_mvp_15_17)
```

>    {2015: 'Cam Newton', 2016: 'Matt Ryan', 2017: 'Tom Brady', 2018: 'Patrick Mahomes', 2019: 'Lamar Jackson', 2020: 'Aaron Rodgers'}

