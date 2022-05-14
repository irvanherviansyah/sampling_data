#DOWNLOAD FILE

wget https://github.com/labusiam/dataset/raw/main/weather_data.xlsx


#Konversi sheet weather_2014 menjadi file weather_2014.csv

in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv


#Konversi sheet weather_2015 menjadi file weather_2015.csv

in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv


#Menggabungkan weather_2014.csv dan weather_2015.csv menjadi weather.csv

csvstack weather_2014.csv weather_2015.csv > weather.csv


#Menghapus weather_data.xlsx

rm weather_data.xlsx


#menjalankan sample dengan rate 0.3, sekaligus menyimpan hasilnya sebagai sample_weather.csv

csvlook weather.csv | sample -r 0.3 > sample_weather.csv
