# Pandas_tricks_python
Pandas trip and tricks in python
# Pandas Trips and Trick
## how to import library
```python 
import seaborn as sns`
```
## seabor k dataset (titanic) ko import download kesy kran
```python
kashati = sns.load_dataset('titanic')
kashati
```
## iris k dataset ko download krne lgy
```python
phool= sns.load_dataset('iris')
phool
```
## apany local directory may phool k dataset ko save krne lagy
```python
kashati.to_excel('kashati.xlsx')
```
## kisi dosare folder/directory may phool k dataset ki file ko save krne lgy
```python
kashati.to_excel('../Day_08/kashati.xlsx')
```
## ab hum ny jo kashati ka dataset kisi aur folder may save kiya the usko kesy apnay curent folder may import krna, aur usko kisi variable may save krna like df may
```python
df = pd.read_excel('kashati.xlsx')
df
```
## kashati k dataset ka Sar(Head) kesy daikhn h?
```python
df.head()
```
## jo dataset df may store kiya h usk coloumn daikhny k liye
```python
df.columns
```
## df may specific coloum ki values daikhny k liye, ya df may sy aik coloum ko print kesy kare? (isko one dim 1D data b bolty h)
```python
df['embark_town']
```
## df may aik sy zadia coloum ki values daikhny k liye, ya df may sy aik sy zadia coloum ko print kesy kare(isko two dim 2D data b bolty h)
```python
df[['survived','who','sex']]
```
## kisi coloum(embark_town) may unique value ko check krne k liye
```python
df.embark_town.unique()
```
## describe function may sirf int/number aur float/decimal ko daikhty hain 
```python
df.describe()
```
## kashtai k dataset may sy kisi b coloum ko delete krne k liye
```python
df =df.drop(columns= 'Unnamed: 0')
df
```
## groupby ka mtlab ye hota h k aik coloum k andar jitni unique values hain uski base pe unko alag kar do  
```python
df.groupby('sex').describe()
```
## transpose krne ka tariqa dataset may mtlb rows ko coloum nay and same coloum ko row may tabdeel krna
```python
df.groupby('sex').describe().T
```
## Count the numbers of survived = 1 grouped by sex(male or female)
```python
df.groupby(['sex','survived']).count()
df.groupby(['sex', 'survived'])['survived'].count()
```
## kashtai k dataset ko groupby aur unique k function sy countplot draw kesy krna
```python
sns.countplot(x="survived", data=df)
```
## hue ka mtlb hota k colors krna plot may coloumns ko 
```python
sns.countplot(x="survived", hue='who', data=df)
```
