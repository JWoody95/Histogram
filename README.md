# Histogram
#Histgram code

from matplotlib import pyplot as plt

grades = [83, 95, 91, 87, 70, 0, 85, 82, 100, 67, 73, 77, 0]

decile = lambda grade: grade // 10 * 10

histogram = (decile(grade) for grade in grades)

plt.bar([x - 4 for x in histogram.keys()], #Shift each bar to the left by 4
         histogram.values(), #give each bar it's correct height 
         8) #give each bar a width of eight
         
plt.axis([-5, 105, 0, 5]) #x-axis from -5 - 105, y-axis from 0 - 5

plt.xticks([i * 10 for i in range(11)]) #x-axis labels at 10, 20, ...

plt.title('Grade Distribution')
plt.xlabel('Decile')
plt.ylabel('# of Students')
plt.show()
