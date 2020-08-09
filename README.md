# bingau

bingau is a Python package for dealing with Binomial and Gaussian distibutions, hence the name.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install bingau.

```bash
pip install bingau
```

## Prerequisite

The package requires matplotlib preinstalled. Install matplotlib using 

```bash
pip install matplotlib
```

## Usage

The package can be used for easy representation of Binomial and Gaussian variables. Magic functons are utilised
for easily adding two Gaussian distributions and two Binomial distributions as well as printing them. 

##### Gaussian

```python
import bingau

g1 = bingau.Gaussian(25,2)                                    #Initiate a Gaussian distribution. Positional arguments: (Mu, Sigma)

g1.data = [1, 3, 99, 100, 120, 32, 330, 23, 76, 44, 31]       #Sample data input
g1.calculate_mean()                                           #Mean
g1.calculate_stdev(True)                                      #Standard deviation
g1.plot_histogram()                                           #Plot histogram
g1.pdf(1.1)                                                   #pdf calculator at a point x, here x = 1.1
g1.plot_histogram_pdf(50)                                     #Function to plot the normalized histogram of the data and a plot of the 
                                                              #probability density function along the same range
                                                           
g2 = bingau.Gaussian(50,1.2)                                  #Second Gaussian distribution

g5 = g1 + g2                                                  #Easily add two Gaussian distributions
print(g5)                                                     #Prints the mean and std-dev of the resultant Gaussian distribution

```

##### Binomial

```python
import bingau

g3 = bingau.Binomial(0.4,20)                                  #Initiate a Binomial distribution. Positional arguments: (p, n)

g3.data = [0, 1, 1, 1, 1, 1, 0, 1, 0, 1, 0, 1, 0]             #Sample data input
g3.calculate_mean()                                           #Mean
g3.calculate_stdev()                                          #Standard deviation
g3.replace_stats_with_data()                                  #Function to calculate p and n from the data set
g3.plot_bar()                                                 #Function to output a histogram of the instance variable data using matplotlib pyplot library
g3.pdf(1.1)                                                   #pdf calculator at a point x, here x = 1.1
g3.plot_bar_pdf()                                             #Function to plot the pdf of the binomial distribution
                                                           
g4 = bingau.Binomial(0.5,50)                                  #Second Binomial distribution

g6 = g3 + g4                                                  #Easily add two Binomial distributions
print(g6)                                                     #Prints the mean and std-dev of the resultant Binomial distribution

```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
