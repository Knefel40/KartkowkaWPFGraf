<Window x:Class="grafika.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:grafika"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <TabControl>
            <TabItem Header="Przyciski Karuzela">
                <UniformGrid Rows="1">
                    <Button Margin="30" Click="Button_Click">Nazot</Button>
                    <Image Source="grafika/MicrosoftTeams-image (0).png" x:Name="obrazek"></Image>
                    <Button Margin="30" Click="Button_Click_1">Dalej</Button>
                </UniformGrid>
            </TabItem>
            <TabItem Header="Radio">
                <StackPanel Orientation="Horizontal">
                    <StackPanel>
                        <RadioButton GroupName="obrazki_radio" x:Name="rys1" Checked="rys1_Checked">Zdjęcie 1</RadioButton>
                        <RadioButton GroupName="obrazki_radio" x:Name="rys2" Checked="rys2_Checked">Zdjęcie 2</RadioButton>
                        <RadioButton GroupName="obrazki_radio" x:Name="rys3" Checked="rys3_Checked">Zdjęcie 3</RadioButton>
                    </StackPanel>
                    <Image Source="grafika/MicrosoftTeams-image (0).png" x:Name="obrazek2"></Image>
                </StackPanel>
            </TabItem>
            <TabItem Header="ComboBox">
                <StackPanel>
                    <ComboBox x:Name="combo_box" SelectionChanged="combo_box_SelectionChanged">
                        <ComboBoxItem>1</ComboBoxItem>
                        <ComboBoxItem>2</ComboBoxItem>
                        <ComboBoxItem>3</ComboBoxItem>
                        <ComboBoxItem>4</ComboBoxItem>
                    </ComboBox>
                    <Image x:Name="obrazek3" Source="grafika/MicrosoftTeams-image (0).png"></Image>
                    
                    
                </StackPanel>
            </TabItem>
        </TabControl>
    </Grid>

</Window>








using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

namespace grafika
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public List<BitmapImage> Images { get; set; }
        public int Aktualny { get; set; }
        public MainWindow()
        {
            InitializeComponent();
            przygotujObrazy();
            Aktualny = 0;
           
        }

        private void przygotujObrazy()
        {
            Images= new List<BitmapImage>();
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (1).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (2).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (3).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (4).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (5).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (6).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (7).png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/MicrosoftTeams-image (8).png", UriKind.Relative)));
        }

        private void Button_Click(object sender, RoutedEventArgs e)
        {
            Aktualny--;
            if(Aktualny < 0)
            {
                Aktualny = Images.Count - 1;
            }
            obrazek.Source = Images[Aktualny];
        }
        
        private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            Aktualny++;
            if (Aktualny == Images.Count)
            {
                Aktualny = 0;
            }
            obrazek.Source = Images[Aktualny];
        }

        private void rys1_Checked(object sender, RoutedEventArgs e)
        {
            obrazek2.Source = new BitmapImage(new Uri("grafika/MicrosoftTeams-Image (1).png",UriKind.Relative));
        }

        private void rys2_Checked(object sender, RoutedEventArgs e)
        {
            obrazek2.Source = new BitmapImage(new Uri("grafika/MicrosoftTeams-Image (2).png", UriKind.Relative));
        }

        private void rys3_Checked(object sender, RoutedEventArgs e)
        {
            obrazek2.Source = new BitmapImage(new Uri("grafika/MicrosoftTeams-Image (3).png", UriKind.Relative));
        }

        private void combo_box_SelectionChanged(object sender, SelectionChangedEventArgs e)
        {
            int ktory = combo_box.SelectedIndex;
            obrazek3.Source = Images[ktory];
        }
    }
}






MEMORY






<Window x:Class="Memory.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Memory"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">

    <UniformGrid>
        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys1"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys2"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys3"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys4"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys5"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys6"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys7"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys8"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys9"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys10"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys12"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys13"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys14"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys15"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys16"></Image>
        </Button>

        <Button Click="Button_Click" Background="WhiteSmoke">
            <Image Source="grafika/brak.png" Margin="20" x:Name="rys11"></Image>
        </Button>
        

    </UniformGrid>
</Window>






using System;
using System.Collections.Generic;
using System.Linq;
using System.Security.Cryptography.Pkcs;
using System.Text;
using System.Threading;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

namespace Memory
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public List<BitmapImage> Images { get; set; }
        public int Pierwszy { get; set; }
        public int Drugi { get; set; }
        public Image PierwszyObraz { get; set; } 
        public Image DrugiObraz { get; set; }
        public int pkt { get; set; }
        public List<BitmapImage> Cos { get; set; }
        public MainWindow()
        {
            InitializeComponent();
            przygotuj();
            Pierwszy = -1;
            Drugi = -1;
            
        }

        private void przygotuj()
        {
            Images = new List<BitmapImage>();
            Cos = new List<BitmapImage>();
            Images.Add(new BitmapImage(new Uri("grafika/rys1.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys1.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys2.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys2.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys3.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys3.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys4.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys4.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys5.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys5.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys6.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys6.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys7.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys7.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys8.png", UriKind.Relative)));
            Images.Add(new BitmapImage(new Uri("grafika/rys8.png", UriKind.Relative)));
            Cos.Add(new BitmapImage(new Uri("grafika/brak.png", UriKind.Relative)));
            Images = Images.OrderBy(x => Random.Shared.Next()).ToList();
            
        }

        private void Button_Click(object sender, RoutedEventArgs e)
        {
            Button button = sender as Button;
            Image image = (Image)button.Content;
            int ktory = int.Parse(image.Name.Substring(3, image.Name.Length-3))-1;
            image.Source = Images[ktory];
            if (Pierwszy < 0)
            {
                Pierwszy = ktory;
                PierwszyObraz = image;
            }
            else if(ktory != Pierwszy)
            {
                Drugi = ktory;
                DrugiObraz = image;
                MessageBox.Show("Kliknieto dwa");
                if(Images[Pierwszy].UriSource==Images[Drugi].UriSource)
                {
                    pkt++;
                    MessageBox.Show("Takie same, masz już "+pkt+" punktów!");
                    PierwszyObraz.Visibility = Visibility.Hidden;
                    DrugiObraz.Visibility = Visibility.Hidden;
                    
                }
                else
                {
                    PierwszyObraz.Source = new BitmapImage(new Uri("grafika/brak.png", UriKind.Relative));
                    DrugiObraz.Source = new BitmapImage(new Uri("grafika/brak.png", UriKind.Relative));
                }

                Pierwszy = -1;
                Drugi = -1;
            }
        }
    }
}






ZGADYWANIE








<Window x:Class="jakiescos.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:jakiescos"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"></ColumnDefinition>
            <ColumnDefinition Width="*"></ColumnDefinition>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
            <RowDefinition></RowDefinition>
        </Grid.RowDefinitions>

        <Grid Grid.ColumnSpan="2" Grid.Row="0" Visibility="Visible" x:Name="grid1">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="*"></ColumnDefinition>

            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
                <RowDefinition></RowDefinition>
                <RowDefinition></RowDefinition>
            </Grid.RowDefinitions>
            <TextBlock Grid.Row="0" Grid.Column="0">Podaj poczatek</TextBlock>
            <Slider Grid.Row="1" Grid.Column="1" Minimum="0" Maximum="100" x:Name="s1"></Slider>
        </Grid>

        <Grid Grid.ColumnSpan="2" Grid.Row="1" Visibility="Visible" x:Name="grid2">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="*"></ColumnDefinition>

            </Grid.ColumnDefinitions>
            <Grid.RowDefinitions>
                <RowDefinition></RowDefinition>
                <RowDefinition></RowDefinition>
            </Grid.RowDefinitions>
            <TextBlock Grid.Row="0" Grid.Column="0">Podaj koniec</TextBlock>
            <Slider Grid.Row="1" Grid.Column="1" Minimum="100" Maximum="1000" x:Name="s2"></Slider>
        </Grid>

        <Button Grid.ColumnSpan="2" Grid.Row="2" Width="100" Height="50" Click="Losuj" Visibility="Visible" x:Name="g1">Losuj liczbe</Button>

        <TextBlock Grid.Column="0" Grid.Row="3" TextAlignment="Center" FontSize="30" Visibility="Hidden" x:Name="tekst">Podaj liczbe</TextBlock>
        <TextBox Grid.Column="1" Grid.Row="3" Height="60" Width="300" Visibility="Hidden" x:Name="tu"></TextBox>


        <TextBlock Grid.Column="0" Grid.Row="4" Visibility="Hidden" x:Name="tekst2">Z zakresu</TextBlock>
        <Button Grid.Column="1" Grid.Row="4" Width="100" Height="50" Visibility="Hidden" x:Name="g2" Click=">Dalej</Button>
    </Grid>
</Window>






using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;

namespace jakiescos
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        int x = 0;
        int strzal;
        int ile = 0;
        private void Losuj(object sender, RoutedEventArgs e)
        {
            int a = (int)s1.Value;
            int b = (int)s2.Value;
            Random random = new Random();

            x = random.Next(a, b);

            tekst2.Text = "Z zakresu "+a+" - "+b;
            
            tekst.Visibility= Visibility.Visible;
            tekst2.Visibility = Visibility.Visible;
            g1.Visibility = Visibility.Collapsed;
            g2.Visibility = Visibility.Visible;
            grid1.Visibility = Visibility.Collapsed;
            grid2.Visibility = Visibility.Collapsed;
            tu.Visibility = Visibility.Visible;
        }

        private void Dalej(object sender, RoutedEventArgs e)
        {
            if (int.TryParse(tu.Text, out strzal))
            {
                if(strzal == x)
                {
                    MessageBox.Show("Gratulacje trafiles za"+ile+"razem");
                }
                if (strzal < x)
                {
                    MessageBox.Show("Za malo");
                    ile++;
                }
                if (strzal> x)
                {
                    MessageBox.Show("Za duzo");
                    ile++;
                }

            }
        }
    }
}

