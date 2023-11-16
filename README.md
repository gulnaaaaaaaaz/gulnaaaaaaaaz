import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;


class WeatherData {
    private String location;
    private double temperature;
    private String condition;

   

    public String getLocation() {
        return location;
    }

    public void setLocation(String location) {
        this.location = location;
    }

    public double getTemperature() {
        return temperature;
    }

    public void setTemperature(double temperature) {
        this.temperature = temperature;
    }

    public String getCondition() {
        return condition;
    }

    public void setCondition(String condition) {
        this.condition = condition;
    }
}


class WeatherAdapter {
    public static WeatherData adaptFromAPIA(String dataFromAPIA) {
        WeatherData weatherData = new WeatherData();
       
        weatherData.setLocation("LocationA");
        weatherData.setTemperature(72.5);
        weatherData.setCondition("Sunny");
        return weatherData;
    }

    public static WeatherData adaptFromAPIB(String dataFromAPIB) {
        WeatherData weatherData = new WeatherData();
        
        weatherData.setLocation("LocationB");
        weatherData.setTemperature(68.0);
        weatherData.setCondition("Rainy");
        return weatherData;
    }
}

// GUI for the Weather Application
public class WeatherApp {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Weather Application");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new FlowLayout());

        JButton apiAButton = new JButton("Get Weather from APIA");
        JButton apiBButton = new JButton("Get Weather from APIB");
        JLabel resultLabel = new JLabel("Weather Data: ");

        apiAButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                
                String dataFromAPIA = "APIA Data"; // Replace with actual API call
                WeatherData weatherData = WeatherAdapter.adaptFromAPIA(dataFromAPIA);
                resultLabel.setText("Weather Data: " + weatherData.getLocation() + ", " +
                        weatherData.getTemperature() + "°C, " + weatherData.getCondition());
            }
        });

        apiBButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               
                String dataFromAPIB = "APIB Data"; // Replace with actual API call
                WeatherData weatherData = WeatherAdapter.adaptFromAPIB(dataFromAPIB);
                resultLabel.setText("Weather Data: " + weatherData.getLocation() + ", " +
                        weatherData.getTemperature() + "°C, " + weatherData.getCondition());
            }
        });

        frame.add(apiAButton);
        frame.add(apiBButton);
        frame.add(resultLabel);
        frame.setSize(300, 150);
        frame.setVisible(true);
    }
}

![Снимок экрана 2023-10-28 212604](https://github.com/gulnaaaaaaaaz/gulnaaaaaaaaz/assets/149236768/e72b388b-2395-4051-b43b-f7921090f65f)
![Снимок экрана 2023-10-28 212558](https://github.com/gulnaaaaaaaaz/gulnaaaaaaaaz/assets/149236768/a02f47d4-fefa-464a-9006-f87fbd1fcc19)
![Снимок экрана 2023-10-28 212556](https://github.com/gulnaaaaaaaaz/gulnaaaaaaaaz/assets/149236768/5fb1b949-1cd1-4467-87b7-29f98e39fda4)
[I first created the WeatherData cla.txt](https://github.com/gulnaaaaaaaaz/gulnaaaaaaaaz/files/13196193/I.first.created.the.WeatherData.cla.txt)


