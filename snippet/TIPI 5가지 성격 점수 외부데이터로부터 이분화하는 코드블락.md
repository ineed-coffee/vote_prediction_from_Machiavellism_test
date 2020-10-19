외부데이터 링크 : [https://gosling.psy.utexas.edu/scales-weve-developed/ten-item-personality-measure-tipi/](https://gosling.psy.utexas.edu/scales-weve-developed/ten-item-personality-measure-tipi/) 

```python
tipi_threshold_table = {
    'Male':{
        '10s':[3.79,4.47,4.41,4.61,5.43],
        '20s':[3.73,4.5,4.57,4.64,5.49],
        '30s':[3.81,4.55,4.77,4.63,5.49],
        '40s':[3.85,4.7,4.96,4.72,5.41],
        '50s':[3.87,4.89,5.11,4.8,5.39],
        '60s':[3.85,4.95,5.26,4.92,5.37],
        '+70s':[4.21,5.5,5.39,4.84,5.39]
    },
    'Female':{
        '10s':[4.06,4.73,4.52,4.07,5.58],
        '20s':[4.07,4.88,4.78,4.09,5.55],
        '30s':[4.17,5.04,4.97,4.25,5.49],
        '40s':[4.2,5.28,5.18,4.49,5.46],
        '50s':[4.18,5.43,5.35,4.66,5.42],
        '60s':[4.21,5.5,5.39,4.84,5.39],
        '+70s':[4.21,5.5,5.39,4.84,5.39]
    }
}

big_five_personality = ['Extraversion','Agreeableness','Conscientiousness','Emotional Stability','Openness to Experiences']

def binarize_big_5_personality(row):
    for idx,col in enumerate(big_five_personality):
        threshold = tipi_threshold_table[row.gender][row.age_group][idx]
        row[col] = 1 if row[col]>=threshold else 0
    return row

for col in big_five_personality:
    data[col] = np.where(tp_data[col]>tp_data[col].mean(),1,0)
```

