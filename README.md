# project-109
#height
from google.colab import files
data = files.upload()
import pandas as pd
import statistics
import csv

df = pd.read_csv("data.csv")
hl = df['Height(Inches)'].to_list()
h_mean = statistics.mean(hl)
h_stdev = statistics.stdev(hl)



hfirst_stdev_start,hfirst_stdev_end = h_mean - h_stdev, h_mean + h_stdev
hsecond_stdev_start,hsecond_stdev_end = h_mean -(2*h_stdev), h_mean + (2*h_stdev)
hthird_stdev_start,hthird_stdev_end = h_mean -(3*h_stdev), h_mean + (3*h_stdev)

list_h_stdev1 = [result for result in hl if result > hfirst_stdev_start and result < hfirst_stdev_end]
list_h_stdev2 = [result for result in hl if result > hsecond_stdev_start and result < hsecond_stdev_end]
list_h_stdev3 = [result for result in hl if result > hthird_stdev_start and result < hthird_stdev_end]

print("{}% of data lies within the first standard deviaton".format(len(list_h_stdev1)*100.0/len(hl)))
print("{}% of data lies within the second standard deviaton".format(len(list_h_stdev2)*100.0/len(hl)))
print("{}% of data lies within the third standard deviaton".format(len(list_h_stdev3)*100.0/len(hl)))






#weight
from google.colab import files
data = files.upload()
import pandas as pd
import statistics
import csv

df = pd.read_csv("data.csv")
w = df['Weight(Pounds)'].to_list()
w_mean = statistics.mean(w)
w_stdev = statistics.stdev(w)



wfirst_stdev_start,wfirst_stdev_end = w_mean - w_stdev, w_mean + w_stdev
wsecond_stdev_start,wsecond_stdev_end = w_mean -(2*w_stdev), w_mean + (2*w_stdev)
wthird_stdev_start,wthird_stdev_end = w_mean -(3*w_stdev), w_mean + (3*w_stdev)

list_w_stdev1 = [result for result in hl if result > wfirst_stdev_start and result < wfirst_stdev_end]
list_w_stdev2 = [result for result in hl if result > wsecond_stdev_start and result < wsecond_stdev_end]
list_w_stdev3 = [result for result in hl if result > wthird_stdev_start and result < wthird_stdev_end]

print("{}% of data lies within the first standard deviaton".format(len(list_w_stdev1)*100.0/len(hl)))
print("{}% of data lies within the second standard deviaton".format(len(list_w_stdev2)*100.0/len(hl)))
print("{}% of data lies within the third standard deviaton".format(len(list_w_stdev3)*100.0/len(hl)))
