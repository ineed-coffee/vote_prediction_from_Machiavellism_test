```python
data[['tp02','tp04','tp06','tp08','tp10']]= 7-data[['tp02','tp04','tp06','tp08','tp10']]

data['Extraversion']=(data.tp01+data.tp06)/2
data['Agreeableness']=(data.tp02+data.tp07)/2
data['Conscientiousness']=(data.tp03+data.tp08)/2
data['Emotional Stability']=(data.tp04+data.tp09)/2
data['Openness to Experiences']=(data.tp05+data.tp10)/2
```

