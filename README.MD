# Learn Shell, Bash and Git

1. This command below is to download file `weather_data.xlsx` from url below and the file will saved into folder `data`
 
	wget -P data https://github.com/labusiam/dataset/raw/main/weather_data.xlsx

2. This command below is to convert sheet `weather_2014` and `weather_2015` in `weather_data.xlsx` into 2 file csv `weather_2014.csv` and `weather_2015.csv` inside `data` folder

	in2csv data/weather_data.xlsx --sheet "weather_2014" > data/weather_2014.csv

	in2csv data/weather_data.xlsx --sheet "weather_2015" > data/weather_2015.csv

3. This command below is to merge the seperate csv file from number 2 `weather_2014.csv` and `weather_2015.csv` into 1 file called `weather.csv` inside `data` folder. and remove file excel `weather_data.xlsx` from `data` folder.

	csvstack data/weather_2014.csv data/weather_2015.csv > data/weather.csv | rm data/weather_data.xlsx

4. This command below is to get 30% sampling data from file `weather.csv` and save them into file called `sample_weather.csv`

	cat data/weather.csv | sample -r 0.3 > data/sample_weather.csv
