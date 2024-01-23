# код без ошибок
## XAMl
<Window x:Class="ColorPicker.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Color Picker" Height="300" Width="400">
    <Grid>
        <Rectangle x:Name="colorRectangle" Fill="Black" HorizontalAlignment="Center" VerticalAlignment="Top" Width="256" Height="108" Margin="59,16,77,0"/>
        <Slider x:Name="redSlider" Minimum="0" Maximum="255" Value="0" HorizontalAlignment="Left" VerticalAlignment="Center" Width="256" Margin="59,143,0,105"/>
        <Slider x:Name="greenSlider" Minimum="0" Maximum="255" Value="0" HorizontalAlignment="Left" VerticalAlignment="Center" Width="256" Margin="59,165,0,83"/>
        <Slider x:Name="blueSlider" Minimum="0" Maximum="255" Value="0" HorizontalAlignment="Left" VerticalAlignment="Center" Width="256" Margin="59,187,0,61"/>
        <TextBox x:Name="rgbTextBox" HorizontalAlignment="Left" VerticalAlignment="Bottom" Width="150" Margin="217,0,0,26"/>
        <TextBox x:Name="hexTextBox" HorizontalAlignment="Left" VerticalAlignment="Bottom" Width="150" Margin="24,0,0,26"/>
    </Grid>
</Window>

## CS

using System;
using System.Windows;
using System.Windows.Media;

namespace ColorPicker
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            redSlider.ValueChanged += UpdateColor;
            greenSlider.ValueChanged += UpdateColor;
            blueSlider.ValueChanged += UpdateColor;
        }

        private void UpdateColor(object sender, RoutedPropertyChangedEventArgs<double> e)
        {
            byte red = (byte)redSlider.Value;
            byte green = (byte)greenSlider.Value;
            byte blue = (byte)blueSlider.Value;

            colorRectangle.Fill = new SolidColorBrush(Color.FromRgb(red, green, blue));
            rgbTextBox.Text = $"RGB: {red}, {green}, {blue}";
            hexTextBox.Text = $"#{red:X2}{green:X2}{blue:X2}";
        }
    }
}


# код с ошибками
## XAMl
<Window x:Class="ColorPicker.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="Color Picker" Height="300" Width="400">
    <Grid>
        // 3 ошибки 
        <Rectangle x:Name="colorRectangleEEEE" Fill="Bleck" HorizontalAlignment="Senter" VerticalAlignment="Top" Width="256" Height="108" Margin="59,16,77,0"/>
        <Slider x:Name="redSlider" Minimum="0" Maximum="255" Value="0" HorizontalAlignment="Left" VerticalAlignment="Center" Width="256" Margin="59,143,0,105"/>
        <Slider x:Name="greenSlider" Minimum="0" Maximum="255" Value="0" HorizontalAlignment="Left" VerticalAlignment="Center" Width="256" Margin="59,165,0,83"/>
        <Slider x:Name="blueSlider" Minimum="0" Maximum="255" Value="0" HorizontalAlignment="Left" VerticalAlignment="Center" Width="256" Margin="59,187,0,61"/>
        <TextBox x:Name="rgbTextBox" HorizontalAlignment="Left" VerticalAlignment="Bottom" Width="150" Margin="217,0,0,26"/>
        <TextBox x:Name="hexTextBox" HorizontalAlignment="Left" VerticalAlignment="Bottom" Width="150" Margin="24,0,0,26"/>
    </Grid>
</Window>



## CS
using System.Windowssss;
using System.Windows.Media;

namespace ColorPicker
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            redSlider.ValueChanged += UpdateColor;
            greenSlider.ValueChanged += UpdateColor;
            blueSlider.ValueChanged += UpdateColor;
        }

        private void UpdateColor(object sender, RoutedPropertyChangedEventArgs<doubbbble> e)
        {
            byte red = (byte)redSlider.Value;
            byte green = (byte)greenSlider.Value;
            byte blue = (byte)blueSlider.Value;
            // у rgb 3 цвета red, green, blue
            colorRectangle.Fill = new SolidColorBrush(Color.FromRgb(red, blue));
            rgbTextBox.Text = $"RGB: {red}, {blue}";
            hexTextBox.Text = $"#{red:X2}{green:X2}{blue:X1000000000}";
        }
    }
}
