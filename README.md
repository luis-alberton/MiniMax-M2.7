<Window x:Class="RadioDj_Lunimar.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:RadioDj_Lunimar"
        
        mc:Ignorable="d"
        Title="🎙️ RadioDJ Lunimar" 
        MinWidth="1024" MinHeight="768"
        Width="1400" Height="640"
        WindowStartupLocation="CenterScreen"
        Background="#1a1a2e"
        WindowStyle="None" 
        ResizeMode="CanResizeWithGrip"
        BorderThickness="1" BorderBrush="#0f3460"><Grid Background="#1a1a2e" x:Name="grdRoot">

    <Grid.Resources>
        <!-- Paleta de Colores -->
        <Color x:Key="PrimaryColor">#16213e</Color>
        <Color x:Key="SecondaryColor">#0f3460</Color>
        <Color x:Key="AccentColor">#e94560</Color>
        <Color x:Key="SuccessColor">#00d9a5</Color>
        <Color x:Key="WarningColor">#ffc107</Color>
        <Color x:Key="TextColor">#f1f1f1</Color>
        <Color x:Key="TextMutedColor">#a0a0a0</Color>

        <SolidColorBrush x:Key="PrimaryBrush" Color="{StaticResource PrimaryColor}"/>
        <SolidColorBrush x:Key="SecondaryBrush" Color="{StaticResource SecondaryColor}"/>
        <SolidColorBrush x:Key="AccentBrush" Color="{StaticResource AccentColor}"/>
        <SolidColorBrush x:Key="SuccessBrush" Color="{StaticResource SuccessColor}"/>
        <SolidColorBrush x:Key="WarningBrush" Color="{StaticResource WarningColor}"/>
        <SolidColorBrush x:Key="TextBrush" Color="{StaticResource TextColor}"/>
        <SolidColorBrush x:Key="TextMutedBrush" Color="{StaticResource TextMutedColor}"/>

        <!-- Estilo Base para Botones de Ventana -->
        <Style x:Key="WindowControlButton" TargetType="Button">
            <Setter Property="Background" Value="Transparent"/>
            <Setter Property="Foreground" Value="{StaticResource TextBrush}"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border x:Name="btnBorder" Background="{TemplateBinding Background}">
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                        <ControlTemplate.Triggers>
                            <Trigger Property="IsMouseOver" Value="True">
                                <Setter TargetName="btnBorder" Property="Background" Value="#3a3a5a"/>
                            </Trigger>
                        </ControlTemplate.Triggers>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>

        <!-- Estilo para botón del Cart Wall -->
        <Style x:Key="CartButton" TargetType="Button">
            <Setter Property="Background" Value="{StaticResource SecondaryBrush}"/>
            <Setter Property="Foreground" Value="{StaticResource TextBrush}"/>
            <Setter Property="BorderThickness" Value="1"/>
            <Setter Property="BorderBrush" Value="#3a3a5a"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="Height" Value="70"/>
            <Setter Property="Margin" Value="5"/>
            <Setter Property="Padding" Value="5"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" 
                                    BorderBrush="{TemplateBinding BorderBrush}"
                                    BorderThickness="{TemplateBinding BorderThickness}"
                                    CornerRadius="8"
                                    Padding="{TemplateBinding Padding}">
                            <StackPanel>
                                <TextBlock x:Name="txtNumber" Text="1" FontSize="14" FontWeight="Bold" 
                                               HorizontalAlignment="Left" Foreground="{StaticResource AccentBrush}"/>
                                <TextBlock x:Name="txtTitle" Text="Botón 1" FontSize="11" FontWeight="SemiBold"
                                               TextWrapping="Wrap" TextAlignment="Center" Margin="0,5,0,0"/>
                                <TextBlock x:Name="txtStatus" Text="Sin audio" FontSize="9" Opacity="0.7"
                                               TextWrapping="Wrap" TextAlignment="Center"/>
                            </StackPanel>
                        </Border>
                        <ControlTemplate.Triggers>
                            <Trigger Property="IsMouseOver" Value="True">
                                <Setter Property="Background" Value="#3a3a5a"/>
                            </Trigger>
                            <Trigger Property="IsPressed" Value="True">
                                <Setter Property="Background" Value="#0f3460"/>
                            </Trigger>
                        </ControlTemplate.Triggers>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>

        <!-- Estilo para botón Verde Gradiente - VERTICAL -->
        <Style x:Key="GreenGradientButton" TargetType="Button">
            <Setter Property="Background">
                <Setter.Value>
                    <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                        <GradientStop Color="#00d9a5" Offset="0"/>
                        <GradientStop Color="#00b894" Offset="0.5"/>
                        <GradientStop Color="#00a885" Offset="1"/>
                    </LinearGradientBrush>
                </Setter.Value>
            </Setter>
            <Setter Property="Foreground" Value="#1a1a2e"/>
            <Setter Property="Padding" Value="12,6"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="FontWeight" Value="SemiBold"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" 
                                    Padding="{TemplateBinding Padding}"
                                    CornerRadius="6">
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
            <Style.Triggers>
                <Trigger Property="IsMouseOver" Value="True">
                    <Setter Property="Background">
                        <Setter.Value>
                            <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                                <GradientStop Color="#0be881" Offset="0"/>
                                <GradientStop Color="#00d9a5" Offset="0.5"/>
                                <GradientStop Color="#00c496" Offset="1"/>
                            </LinearGradientBrush>
                        </Setter.Value>
                    </Setter>
                </Trigger>
                <Trigger Property="IsPressed" Value="True">
                    <Setter Property="Background">
                        <Setter.Value>
                            <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                                <GradientStop Color="#00a885" Offset="0"/>
                                <GradientStop Color="#009574" Offset="0.5"/>
                                <GradientStop Color="#008363" Offset="1"/>
                            </LinearGradientBrush>
                        </Setter.Value>
                    </Setter>
                </Trigger>
            </Style.Triggers>
        </Style>

        <!-- Estilo para botón Verde Gradiente claro - VERTICAL -->
        <Style x:Key="LightGreenGradientButton" TargetType="Button">
            <Setter Property="Background">
                <Setter.Value>
                    <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                        <GradientStop Color="#55efc4" Offset="0"/>
                        <GradientStop Color="#00d9a5" Offset="0.5"/>
                        <GradientStop Color="#00b894" Offset="1"/>
                    </LinearGradientBrush>
                </Setter.Value>
            </Setter>
            <Setter Property="Foreground" Value="#1a1a2e"/>
            <Setter Property="Padding" Value="12,6"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="FontWeight" Value="SemiBold"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" 
                                    Padding="{TemplateBinding Padding}"
                                    CornerRadius="6">
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
            <Style.Triggers>
                <Trigger Property="IsMouseOver" Value="True">
                    <Setter Property="Background">
                        <Setter.Value>
                            <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                                <GradientStop Color="#81ecec" Offset="0"/>
                                <GradientStop Color="#55efc4" Offset="0.5"/>
                                <GradientStop Color="#00d9a5" Offset="1"/>
                            </LinearGradientBrush>
                        </Setter.Value>
                    </Setter>
                </Trigger>
            </Style.Triggers>
        </Style>

        <!-- Estilo para botón Verde Gradiente Oscuro - VERTICAL -->
        <Style x:Key="DarkGreenGradientButton" TargetType="Button">
            <Setter Property="Background">
                <Setter.Value>
                    <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                        <GradientStop Color="#0b6623" Offset="0"/>
                        <GradientStop Color="#17c964" Offset="0.5"/>
                        <GradientStop Color="#0b6623" Offset="1"/>
                    </LinearGradientBrush>
                </Setter.Value>
            </Setter>
            <Setter Property="Foreground" Value="White"/>
            <Setter Property="Padding" Value="12,6"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="FontWeight" Value="SemiBold"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" 
                                    Padding="{TemplateBinding Padding}"
                                    CornerRadius="6">
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
            <Style.Triggers>
                <Trigger Property="IsMouseOver" Value="True">
                    <Setter Property="Background">
                        <Setter.Value>
                            <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                                <GradientStop Color="#17c964" Offset="0"/>
                                <GradientStop Color="#1a9e4a" Offset="0.5"/>
                                <GradientStop Color="#0b6623" Offset="1"/>
                            </LinearGradientBrush>
                        </Setter.Value>
                    </Setter>
                </Trigger>
            </Style.Triggers>
        </Style>

        <!-- Estilo para botón Verde Gradiente con brillo - VERTICAL -->
        <Style x:Key="ShinyGreenGradientButton" TargetType="Button">
            <Setter Property="Background">
                <Setter.Value>
                    <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                        <GradientStop Color="#00ffcc" Offset="0"/>
                        <GradientStop Color="#00d9a5" Offset="0.3"/>
                        <GradientStop Color="#00b894" Offset="0.7"/>
                        <GradientStop Color="#009574" Offset="1"/>
                    </LinearGradientBrush>
                </Setter.Value>
            </Setter>
            <Setter Property="Foreground" Value="#1a1a2e"/>
            <Setter Property="Padding" Value="12,6"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="FontWeight" Value="Bold"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" 
                                    Padding="{TemplateBinding Padding}"
                                    CornerRadius="8">
                            <Border.Effect>
                                <DropShadowEffect BlurRadius="5" ShadowDepth="1" Opacity="0.3" Color="Black"/>
                            </Border.Effect>
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
        </Style>

        <!-- Estilos de Interfaz -->
        <Style x:Key="PrimaryButton" TargetType="Button">
            <Setter Property="Background" Value="{StaticResource AccentBrush}"/>
            <Setter Property="Foreground" Value="White"/>
            <Setter Property="Padding" Value="15,8"/>
            <Setter Property="BorderThickness" Value="0"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="MinWidth" Value="80"/>
            <Setter Property="Template">
                <Setter.Value>
                    <ControlTemplate TargetType="Button">
                        <Border Background="{TemplateBinding Background}" Padding="{TemplateBinding Padding}">
                            <ContentPresenter HorizontalAlignment="Center" VerticalAlignment="Center"/>
                        </Border>
                    </ControlTemplate>
                </Setter.Value>
            </Setter>
            <Style.Triggers>
                <Trigger Property="IsMouseOver" Value="True">
                    <Setter Property="Background" Value="#ff6b8a"/>
                </Trigger>
            </Style.Triggers>
        </Style>

        <Style x:Key="ModeButton" TargetType="ToggleButton">
            <Setter Property="Background" Value="{StaticResource SecondaryBrush}"/>
            <Setter Property="Foreground" Value="{StaticResource TextBrush}"/>
            <Setter Property="Padding" Value="12,6"/>
            <Setter Property="BorderThickness" Value="1"/>
            <Setter Property="BorderBrush" Value="#3a3a5a"/>
            <Setter Property="Cursor" Value="Hand"/>
            <Setter Property="MinWidth" Value="90"/>
        </Style>

        <BooleanToVisibilityConverter x:Key="BoolToVisibility"/>

    </Grid.Resources>

    <Grid.RowDefinitions>
        <RowDefinition Height="Auto" MinHeight="50"/>
        <RowDefinition Height="Auto" MinHeight="40"/>
        <RowDefinition Height="*" MinHeight="400"/>
        <RowDefinition Height="Auto" MinHeight="70"/>
        <RowDefinition Height="Auto" MinHeight="30"/>
    </Grid.RowDefinitions>

    <!-- ============ HEADER ============ -->
    <!-- ============ HEADER ============ -->
    <Border x:Name="hdrMain" Grid.Row="0" Background="{StaticResource PrimaryBrush}" 
        BorderBrush="#3a3a5a" BorderThickness="0,0,0,1"
        MouseLeftButtonDown="Header_MouseDown">
        <Grid Margin="15,5">
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="Auto" MinWidth="200"/>
                <ColumnDefinition Width="*"/>
                <ColumnDefinition Width="Auto" MinWidth="200"/>
            </Grid.ColumnDefinitions>

                <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                    <TextBlock Text="🎙️" Foreground="Yellow" FontSize="24" Margin="0,0,10,0"/>
                    <StackPanel>
                        <TextBlock Text="RadioDJ Lunimar" FontWeight="Bold" FontSize="18" Foreground="{StaticResource TextBrush}"/>
                        <TextBlock Text="Professional Radio Automation" FontSize="11" Foreground="Red"/>
                    </StackPanel>
                </StackPanel>
                <StackPanel Grid.Column="2" Orientation="Horizontal" VerticalAlignment="Center" HorizontalAlignment="Right">
                <TextBlock Text="👤 Admin" Foreground="{StaticResource TextBrush}" Margin="0,0,15,0"/>
                <TextBlock x:Name="txtClock" Text="12:00:00" FontWeight="Bold" Foreground="{StaticResource AccentBrush}" Margin="0,0,15,0"/>

                <Button x:Name="btnMinimize" Content="─" Width="35" Height="28" 
        Click="BtnMinimize_Click"
        Style="{StaticResource WindowControlButton}" 
        FontSize="18" FontWeight="Bold" Margin="0,0,2,0" ToolTip="Minimizar"/>

                <Button x:Name="btnMaximize" Content="☐" Width="35" Height="28" 
        Click="BtnMaximize_Click"
        Style="{StaticResource WindowControlButton}" 
        FontSize="14" Margin="0,0,2,0" ToolTip="Maximizar"/>

                <Button x:Name="btnClose" Content="❌" Width="35" Height="28" 
        Click="BtnClose_Click"
        FontSize="12" ToolTip="Cerrar">
                    <Button.Style>
                        <Style TargetType="Button" BasedOn="{StaticResource WindowControlButton}">
                            <Setter Property="Foreground" Value="#ff6b6b"/>
                            <Style.Triggers>
                                <Trigger Property="IsMouseOver" Value="True">
                                    <Setter Property="Background" Value="#ff6b6b"/>
                                    <Setter Property="Foreground" Value="White"/>
                                </Trigger>
                            </Style.Triggers>
                        </Style>
                    </Button.Style>
                </Button>
            </StackPanel>
        </Grid>
    </Border>

    <!-- ============ MODE SELECTOR & STATUS ============ -->
    <Border Grid.Row="1" Background="{StaticResource SecondaryBrush}" Padding="10,8">
        <ScrollViewer HorizontalScrollBarVisibility="Auto" VerticalScrollBarVisibility="Disabled">
            <Grid MinWidth="750">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto"/>
                    <ColumnDefinition Width="Auto"/>
                    <ColumnDefinition Width="Auto"/>
                </Grid.ColumnDefinitions>

                <StackPanel Orientation="Horizontal" VerticalAlignment="Center">
                    <TextBlock Text="Modo:" Foreground="{StaticResource TextMutedBrush}" VerticalAlignment="Center" Margin="0,0,5,0"/>
                    <ToggleButton x:Name="btnAutoMode" Content="🤖 AUTO" Style="{StaticResource ModeButton}" IsChecked="True" Margin="0,0,5,0"/>
                    <ToggleButton x:Name="btnLiveMode" Content="🎧 LIVE ASSIST" Style="{StaticResource ModeButton}" Margin="0,0,5,0"/>
                    <ToggleButton x:Name="btnRebroadcastMode" Content="📡 REBROADCAST" Style="{StaticResource ModeButton}"/>
                </StackPanel>

                <Border Grid.Column="1" Background="#252542" Margin="10,0" Padding="10">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="Auto"/>
                            <ColumnDefinition Width="*" MaxWidth="300"/>
                            <ColumnDefinition Width="Auto"/>
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="🎵 :" Foreground="{StaticResource TextMutedBrush}" 
                                   VerticalAlignment="Center"/>
                        <TextBlock Grid.Column="1" x:Name="txtNowPlaying" Text="---" FontWeight="SemiBold" 
                                       Foreground="{StaticResource TextBrush}" Width="150" VerticalAlignment="Center" Margin="10,0"
                                       TextTrimming="CharacterEllipsis" TextWrapping="NoWrap"
                                       ToolTip="{Binding Text, RelativeSource={RelativeSource Self}}"/>
                        <StackPanel Grid.Column="2" Orientation="Horizontal">
                            <TextBlock x:Name="txtCurrentTime" Text="00:00 / 00:00" Foreground="{StaticResource TextMutedBrush}" Margin="0,0,15,0"/>
                            <ProgressBar x:Name="progressBar" Width="200" Height="6" Value="0" 
                                             Background="#3a3a5a" Foreground="{StaticResource AccentBrush}"/>
                        </StackPanel>
                    </Grid>
                </Border>

                <StackPanel Grid.Column="2" Orientation="Horizontal" VerticalAlignment="Center">
                    <Border Background="#252542" Padding="0,4" Margin="5,0">
                            <TextBlock x:Name="txtPlaylistInfo" 
                                        Text="📊 Playlist: 0 tracks | ⏱️ Total: 00:00" 
                                        Foreground="{StaticResource TextBrush}" 
                                        FontSize="11"/>
                        </Border>
                    <Border x:Name="borderProxComercial" Background="#252542" Padding="8,4" Margin="5,0" CornerRadius="4">
                        <TextBlock x:Name="txtProxComercial" Text="📢 Próx. Evento: --:--" Foreground="{StaticResource WarningBrush}" FontSize="11"/>
                    </Border>
                </StackPanel>
            </Grid>
        </ScrollViewer>
    </Border>

    <!-- ============ MAIN CONTENT AREA ============ -->
    <Grid Grid.Row="2" x:Name="grdMainContent">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="280" MinWidth="200" x:Name="colLibrary"/>
            <ColumnDefinition Width="*" MinWidth="300" x:Name="colPlaylist"/>
            <ColumnDefinition Width="320" MinWidth="250" x:Name="colTools"/>
        </Grid.ColumnDefinitions>

        <!-- Toggle Paneles -->
        <StackPanel Grid.Row="2" Grid.ColumnSpan="3" VerticalAlignment="Top" HorizontalAlignment="Right" Margin="0,5,10,0" Orientation="Horizontal">
            <Button Content="📚" ToolTip="Biblioteca" Width="30" Height="25" Background="#252542" Foreground="White" BorderThickness="0" Cursor="Hand" Click="ToggleLibraryPanel"/>
            <Button Content="🎛️" ToolTip="Herramientas" Width="30" Height="25" Background="#252542" Foreground="White" BorderThickness="0" Cursor="Hand" Click="ToggleToolsPanel" Margin="5,0,0,0"/>
        </StackPanel>

        <!-- LEFT PANEL: Explorador y Buscador -->
        <!-- LEFT PANEL: Explorador y Buscador -->
        <!-- LEFT PANEL: Explorador y Buscador -->
        <Border x:Name="pnlLibrary" Grid.Column="0" Background="{StaticResource PrimaryBrush}" BorderBrush="#3a3a5a" BorderThickness="0,0,1,0">
            <TabControl Background="Transparent" BorderThickness="0" Foreground="{StaticResource TextBrush}">

                <!-- TAB 1: Explorador de Archivos en Árbol -->
<TabItem Header="🖥️ Explorador">
    <Grid Margin="10">
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>

        <!-- Barra de dirección -->
        <StackPanel Orientation="Horizontal" Margin="0,0,0,10">
            <Button x:Name="btnGoUp" Content="⬆️" Width="30" Height="30" 
                    Background="#0f3460" Foreground="White" BorderThickness="0" 
                    Cursor="Hand" ToolTip="Subir carpeta" Click="BtnGoUp_Click"/>
            <TextBox x:Name="txtCurrentPath" 
                     Background="#252542" Foreground="White" BorderThickness="0" 
                     Padding="8" Margin="5,0,0,0" FontSize="11"
                     KeyDown="TxtCurrentPath_KeyDown"/>
        </StackPanel>

        <!-- TreeView con scroll incorporado - CORREGIDO -->
        <TreeView x:Name="tvFileExplorer" 
                  Grid.Row="1"
                  Background="#16213e" 
                  BorderThickness="0"
                  SelectedItemChanged="TvFileExplorer_SelectedItemChanged"
                  ScrollViewer.CanContentScroll="True"
                  ScrollViewer.HorizontalScrollBarVisibility="Auto"
                  ScrollViewer.VerticalScrollBarVisibility="Auto">
            <TreeView.Resources>
                <!-- Estilo para items del TreeView -->
                <Style TargetType="TreeViewItem">
                    <Setter Property="Foreground" Value="White"/>
                    <Setter Property="FontSize" Value="12"/>
                    <Setter Property="FontWeight" Value="Bold"/>
                    <Setter Property="IsExpanded" Value="False"/>
                    <Setter Property="BorderThickness" Value="0"/>
                    <Setter Property="Padding" Value="3"/>
                    <Style.Triggers>
                        <Trigger Property="Header" Value="🖥️ Este equipo">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="📁 Documentos">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="🎵 Música">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="📥 Descargas">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="⭐ Favoritos">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="🖼️ Imágenes">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="🎬 Vídeos">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                        <Trigger Property="Header" Value="📌 Escritorio">
                            <Setter Property="Foreground" Value="White"/>
                            <Setter Property="FontWeight" Value="Bold"/>
                        </Trigger>
                    </Style.Triggers>
                </Style>
            </TreeView.Resources>
        </TreeView>
    </Grid>
</TabItem>

                <!-- TAB 2: Buscador -->
                <TabItem Header="🔍 Buscar">
                    <Grid Margin="10">
                        <Grid.RowDefinitions>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="*"/>
                        </Grid.RowDefinitions>

                        <TextBox x:Name="txtSearchFile" Grid.Row="0" 
                         Background="#252542" Foreground="White" BorderThickness="0" 
                         Padding="8" Margin="0,0,0,10" FontSize="11"
                         KeyDown="TxtSearchFile_KeyDown"/>

                        <WrapPanel Grid.Row="1" Margin="0,0,0,10">
                            <Button x:Name="btnSearchLocal" Content="💻 Esta PC" 
                            Background="#0f3460" Foreground="White" BorderThickness="0" 
                            Padding="6,3" Cursor="Hand" Margin="0,0,5,5" FontSize="10"
                            Click="BtnSearchLocal_Click"/>
                            <Button x:Name="btnSearchMusic" Content="🎵 Música" 
                            Background="#0f3460" Foreground="White" BorderThickness="0" 
                            Padding="6,3" Cursor="Hand" Margin="0,0,5,5" FontSize="10"
                            Click="BtnSearchMusic_Click"/>
                            <Button x:Name="btnSearchDownloads" Content="📥 Descargas" 
                            Background="#0f3460" Foreground="White" BorderThickness="0" 
                            Padding="6,3" Cursor="Hand" Margin="0,0,5,5" FontSize="10"
                            Click="BtnSearchDownloads_Click"/>
                            <Button x:Name="btnSearchDocuments" Content="📄 Documentos" 
                            Background="#0f3460" Foreground="White" BorderThickness="0" 
                            Padding="6,3" Cursor="Hand" Margin="0,0,5,5" FontSize="10"
                            Click="BtnSearchDocuments_Click"/>
                        </WrapPanel>

                        <ListView x:Name="lvSearchResults" Grid.Row="2" Background="#252542" BorderThickness="0"
                          MouseDoubleClick="LvSearchResults_MouseDoubleClick">
                            <ListView.View>
                                <GridView>
                                    <GridViewColumn Header="Nombre" Width="160" DisplayMemberBinding="{Binding Name}"/>
                                    <GridViewColumn Header="Carpeta" Width="120" DisplayMemberBinding="{Binding Path}"/>
                                    <GridViewColumn Header="Tamaño" Width="60" DisplayMemberBinding="{Binding Size}"/>
                                </GridView>
                            </ListView.View>
                            <ListView.ItemContainerStyle>
                                <Style TargetType="ListViewItem">
                                    <Setter Property="Foreground" Value="White"/>
                                    <Setter Property="FontSize" Value="10"/>
                                </Style>
                            </ListView.ItemContainerStyle>
                        </ListView>
                    </Grid>
                </TabItem>

            </TabControl>
        </Border>

        <!-- CENTER PANEL: Playlist & Decks -->
        <Border Grid.Column="1" Background="#1a1a2e">
            <Grid>
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto"/>
                    <RowDefinition Height="*"/>
                    <RowDefinition Height="Auto"/>
                </Grid.RowDefinitions>

                <Border Grid.Row="0" Padding="15,10" Background="{StaticResource SecondaryBrush}">
                    <Grid>
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="Auto"/>
                        </Grid.ColumnDefinitions>
                        <TextBlock Text="📋 Playlist Actual" FontWeight="Bold" Foreground="{StaticResource TextBrush}" TextWrapping="Wrap"/>
                        <StackPanel Grid.Column="1" Orientation="Horizontal">
                                <Button x:Name="btnHora"
                                        Content="🕒"
                                        Style="{StaticResource DarkGreenGradientButton}"
                                        Foreground="White"
                                        Padding="8,4"
                                        BorderThickness="0"
                                        Margin="0,0,5,0"
                                        Cursor="Hand"
                                        FontSize="20"
                                        FontWeight="Bold"
                                        ToolTip="Anuncio del Tiempo"
                                        Click="btnHora_Click"/>

                                <Button x:Name="btnInsertHora" 
                                        Content="🕒 Insertar Hora" 
                                        Style="{StaticResource DarkGreenGradientButton}" 
                                        Foreground="White" 
                                        Padding="8,4" 
                                        BorderThickness="0" 
                                        Margin="0,0,5,0" 
                                        Cursor="Hand" 
                                        FontSize="11" 
                                        FontWeight="SemiBold" 
                                        ToolTip="Insertar marcador de hora en la playlist" 
                                        Click="BtnInsertHora_Click"/>
                            <Button Content="🔄 Generar" Background="#252542" Foreground="White" Padding="8,4" BorderThickness="0" 
                                        Margin="0,0,5,0" Cursor="Hand" FontSize="11" Click="BtnGeneratePlaylist_Click"/>
                            <Button Content="💾 Guardar" Background="#252542" Foreground="White" Padding="8,4" BorderThickness="0" 
                                        Margin="0,0,5,0" Cursor="Hand" FontSize="11" Click="BtnSavePlaylist_Click"/>
                            <Button Content="📤 Exportar" Style="{StaticResource PrimaryButton}" Cursor="Hand" FontSize="11" Click="BtnExportPlaylist_Click"/>
                        </StackPanel>
                    </Grid>
                </Border>

                <ListView x:Name="lvPlaylist" 
                                Grid.Row="1" 
                                Margin="10" 
                                Background="Transparent" 
                                BorderThickness="0"
                                Foreground="{StaticResource TextBrush}" 
                                HorizontalContentAlignment="Stretch"
                                ScrollViewer.HorizontalScrollBarVisibility="Disabled"
                                AllowDrop="True"
                                PreviewMouseLeftButtonDown="LvPlaylist_PreviewMouseLeftButtonDown"
                                PreviewMouseMove="LvPlaylist_PreviewMouseMove"
                                Drop="LvPlaylist_Drop"
                                DragOver="LvPlaylist_DragOver"
                                PreviewKeyDown="LvPlaylist_PreviewKeyDown">
                    <ListView.ItemContainerStyle>
                        <Style TargetType="ListViewItem">
                            <Setter Property="HorizontalContentAlignment" Value="Stretch"/>
                            <Setter Property="Padding" Value="0"/>
                            <Setter Property="Margin" Value="0,3"/>
                            <Setter Property="BorderThickness" Value="0"/>
                            <Setter Property="Background" Value="Transparent"/>
                            <Style.Triggers>
                                <DataTrigger Binding="{Binding IsPlaying}" Value="True">
                                    <Setter Property="Background">
                                        <Setter.Value>
                                            <LinearGradientBrush StartPoint="0,0" EndPoint="0,1">
                                                <GradientStop Color="#0b6623" Offset="0"/>
                                                <GradientStop Color="#17c964" Offset="0.5"/>
                                                <GradientStop Color="#0b6623" Offset="1"/>
                                            </LinearGradientBrush>
                                        </Setter.Value>
                                    </Setter>
                                </DataTrigger>
                            </Style.Triggers>
                        </Style>
                    </ListView.ItemContainerStyle>
                    <ListView.ItemTemplate>
                        <DataTemplate>
                            <Border Padding="12" CornerRadius="6" Margin="0" Background="{Binding RelativeSource={RelativeSource AncestorType=ListViewItem}, Path=Background}">
                                <Grid>
                                    <Grid.ColumnDefinitions>
                                        <ColumnDefinition Width="35"/>
                                        <ColumnDefinition Width="*"/>
                                        <ColumnDefinition Width="Auto"/>
                                        <ColumnDefinition Width="Auto"/>
                                    </Grid.ColumnDefinitions>
                                    <StackPanel VerticalAlignment="Center">
                                        <TextBlock Text="{Binding Position}" FontWeight="Bold" Foreground="White" HorizontalAlignment="Center"/>
                                        <TextBlock Text="🔊" FontSize="10" HorizontalAlignment="Center"/>
                                    </StackPanel>
                                    <StackPanel Grid.Column="1" Margin="10,0">
                                        <TextBlock Text="{Binding Title}" FontWeight="SemiBold" FontSize="13" Foreground="White" 
                                                       TextWrapping="NoWrap" TextTrimming="CharacterEllipsis"/>
                                        <TextBlock Text="{Binding Artist}" FontSize="11" Foreground="#DDDDDD" 
                                                       TextWrapping="NoWrap" TextTrimming="CharacterEllipsis"/>
                                        <TextBlock FontSize="10" Foreground="#DDDDDD" TextWrapping="NoWrap" TextTrimming="CharacterEllipsis">
                                                <Run Text="{Binding Category}"/><Run Text=" • "/><Run Text="{Binding Duration}"/>
                                        </TextBlock>
                                    </StackPanel>
                                    <StackPanel Grid.Column="2" VerticalAlignment="Center" Margin="0,0,10,0">
                                        <TextBlock Text="{Binding Duration}" FontWeight="SemiBold" Foreground="White"/>
                                    </StackPanel>
                                    <StackPanel Grid.Column="3" 
                                                    Orientation="Horizontal" 
                                                    VerticalAlignment="Center">
                                        <Button Content="✏️" 
                                                    Width="28" 
                                                    Background="Transparent" 
                                                    BorderThickness="0" 
                                                    Foreground="White" 
                                                    Cursor="Hand"/>
                                        <Button Content="🗑️" 
                                                    Width="28" 
                                                    Background="Transparent" 
                                                    BorderThickness="0" 
                                                    Foreground="#ff6b6b" 
                                                    Cursor="Hand" 
                                                    Tag="{Binding}" 
                                                    Click="BtnRemoveFromPlaylist_Click"/>
                                    </StackPanel>
                                </Grid>
                            </Border>
                        </DataTemplate>
                    </ListView.ItemTemplate>
                </ListView>

                <!-- Deck Preview -->
                <Border Grid.Row="2" 
                            Background="{StaticResource SecondaryBrush}" 
                            Padding="10" 
                            Margin="10,0,10,10">
                    <Grid x:Name="grdDecks">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="*"/>
                        </Grid.ColumnDefinitions>
                        <Border Background="#252542" 
                                    Padding="8" 
                                    Margin="0,0,5,0">
                            <StackPanel>
                                <TextBlock Text="🔴 DECK A - EN EMISIÓN" 
                                               FontWeight="Bold" 
                                               Foreground="Red" 
                                               FontSize="11"/>
                                <TextBlock x:Name="txtDeckATitle" 
                                               Text="---" 
                                               Foreground="GreenYellow" 
                                               FontWeight="SemiBold" 
                                               Margin="0,5,0,0"/>
                                <TextBlock x:Name="txtDeckAArtist" 
                                               Text="---" 
                                               FontSize="11" 
                                               Foreground="{StaticResource TextMutedBrush}"/>
                                <ProgressBar x:Name="progressDeckA" 
                                                 Height="4" 
                                                 Value="0" 
                                                 Margin="0,8,0,5" 
                                                 Background="#3a3a5a" 
                                                 Foreground="{StaticResource SuccessBrush}"/>
                                <StackPanel Orientation="Horizontal">
                                    <Button Content="⏭️ Skip" 
                                                FontSize="10" 
                                                Padding="5,2" 
                                                Background="Transparent" 
                                                BorderThickness="0" 
                                                Foreground="White" 
                                                Cursor="Hand" 
                                                Click="BtnNext_Click"/>
                                    <Button Content="🎚️ Sweeper" 
                                                FontSize="10" 
                                                Padding="5,2" 
                                                Background="Transparent" 
                                                BorderThickness="0" 
                                                Foreground="{StaticResource WarningBrush}" 
                                                Cursor="Hand"/>
                                </StackPanel>
                            </StackPanel>
                        </Border>
                        <Border Grid.Column="1" 
                                    Background="#252542" 
                                    Padding="8" 
                                    Margin="5,0">
                            <StackPanel>
                                <TextBlock Text="⏭️ DECK B - SIGUIENTE" 
                                               FontWeight="Bold" 
                                               Foreground="{StaticResource TextBrush}" 
                                               FontSize="11"/>
                                <TextBlock x:Name="txtDeckBTitle" 
                                               Text="---" 
                                               Foreground="Yellow" 
                                               FontWeight="SemiBold" 
                                               Margin="0,5,0,0"/>
                                <TextBlock x:Name="txtDeckBArtist" 
                                               Text="---" 
                                               FontSize="11" 
                                               Foreground="{StaticResource TextMutedBrush}"/>
                                <TextBlock x:Name="txtDeckBTime" 
                                               Text="En cola: --:--" 
                                               FontSize="10" 
                                               Foreground="{StaticResource TextMutedBrush}" 
                                               Margin="0,5,0,0"/>
                                <Button Content="⏩ Cambiar" 
                                            FontSize="10" 
                                            Padding="5,2" 
                                            Background="{StaticResource AccentBrush}" 
                                            BorderThickness="0" 
                                            Foreground="White" 
                                            Cursor="Hand" 
                                            Margin="0,5,0,0" 
                                            Click="BtnNext_Click"/>
                            </StackPanel>
                        </Border>
                        <Border Grid.Column="2" 
                                    Background="#252542" 
                                    Padding="8" 
                                    Margin="5,0,0,0">
                            <StackPanel>
                                <TextBlock Text="⏭️ DECK C - DESPUÉS" 
                                               FontWeight="Bold" 
                                               Foreground="{StaticResource TextBrush}" 
                                               FontSize="11"/>
                                <TextBlock x:Name="txtDeckCTitle" 
                                               Text="---" Foreground="Red" 
                                               FontWeight="SemiBold" 
                                               Margin="0,5,0,0"/>
                                <TextBlock x:Name="txtDeckCArtist" 
                                               Text="---" 
                                               FontSize="11" 
                                               Foreground="{StaticResource TextMutedBrush}"/>
                                <TextBlock x:Name="txtDeckCTime" 
                                               Text="Programado: --:--" 
                                               FontSize="10" 
                                               Foreground="{StaticResource TextMutedBrush}" 
                                               Margin="0,5,0,0"/>
                                <Button Content="👁️ Previsualizar" 
                                            FontSize="10" 
                                            Padding="5,2" 
                                            Background="#252542" 
                                            BorderThickness="1" 
                                            BorderBrush="#3a3a5a" 
                                            Foreground="White" 
                                            Cursor="Hand" 
                                            Margin="0,5,0,0"/>
                            </StackPanel>
                        </Border>
                    </Grid>
                </Border>
            </Grid>
        </Border>

        <!-- RIGHT PANEL: Cart Wall & Tools - COMPLETO -->
        <Border x:Name="pnlTools" 
                    Grid.Column="2" 
                    Background="{StaticResource PrimaryBrush}" 
                    BorderBrush="#3a3a5a" 
                    BorderThickness="1,0,0,0">
            <TabControl Background="Transparent" 
                            BorderThickness="0" 
                            Foreground="{StaticResource TextBrush}">
                <!-- TAB 1: Cart Wall con 10 botones -->
                <TabItem Header="🎛️ Cart Wall">
                    <Grid Margin="10">
                        <Grid.RowDefinitions>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="Auto"/>
                        </Grid.RowDefinitions>

                        <StackPanel Orientation="Horizontal" 
                                        Margin="0,0,0,10">
                            <ComboBox x:Name="cmbCartCategory" 
                                          Background="#252542" 
                                          Foreground="Black" 
                                          BorderThickness="0" 
                                          Padding="5" 
                                          Width="120" 
                                          Margin="0,0,5,0" 
                                          FontSize="11" 
                                          SelectionChanged="CmbCartCategory_SelectionChanged">
                                <ComboBoxItem IsSelected="True">📁 Todas</ComboBoxItem>
                                <ComboBoxItem>🎵 Jingles</ComboBoxItem>
                                <ComboBoxItem>🗣️ Sweepers</ComboBoxItem>
                                <ComboBoxItem>🔊 Efectos</ComboBoxItem>
                                <ComboBoxItem>🎙️ Cuñas</ComboBoxItem>
                            </ComboBox>
                            <Button Content="💾" Width="30" 
                                        Background="#252542" 
                                        BorderThickness="0" 
                                        Foreground="White" 
                                        Cursor="Hand" 
                                        ToolTip="Guardar configuración" 
                                        Margin="0,0,5,0" 
                                        Click="BtnSaveCartWall_Click"/>
                            <Button Content="📁" 
                                        Width="30" 
                                        Background="#252542" 
                                        BorderThickness="0" 
                                        Foreground="White" 
                                        Cursor="Hand" 
                                        ToolTip="Cargar configuración" 
                                        Click="BtnLoadCartWall_Click"/>
                        </StackPanel>

                        <!-- Grid de 10 botones ordenados correctamente -->
                        <ScrollViewer Grid.Row="1" VerticalScrollBarVisibility="Auto" HorizontalScrollBarVisibility="Auto">
                            <Grid>
                                <Grid.RowDefinitions>
                                    <RowDefinition Height="Auto"/>
                                    <RowDefinition Height="Auto"/>
                                    <RowDefinition Height="Auto"/>
                                    <RowDefinition Height="Auto"/>
                                    <RowDefinition Height="Auto"/>
                                </Grid.RowDefinitions>
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="*"/>
                                    <ColumnDefinition Width="*"/>
                                </Grid.ColumnDefinitions>

                                <!-- Fila 1: Botón 1 y Botón 2 -->
                                <!-- Fila 1: Botón 1 y Botón 2 -->
                                    <!-- Fila 1: Botón 1 y Botón 2 -->
                                    <Button x:Name="btnCart1" 
        Grid.Row="0" 
        Grid.Column="0" 
        Tag="1" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <Button x:Name="btnCart2" 
        Grid.Row="0" 
        Grid.Column="1" 
        Tag="2" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <!-- Fila 2: Botón 3 y Botón 4 -->
                                    <Button x:Name="btnCart3" 
        Grid.Row="1" 
        Grid.Column="0" 
        Tag="3" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <Button x:Name="btnCart4" 
        Grid.Row="1" 
        Grid.Column="1" 
        Tag="4" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <!-- Fila 3: Botón 5 y Botón 6 -->
                                    <Button x:Name="btnCart5" 
        Grid.Row="2" 
        Grid.Column="0" 
        Tag="5" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <Button x:Name="btnCart6" 
        Grid.Row="2" 
        Grid.Column="1" 
        Tag="6" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <!-- Fila 4: Botón 7 y Botón 8 -->
                                    <Button x:Name="btnCart7" 
        Grid.Row="3" 
        Grid.Column="0" 
        Tag="7" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <Button x:Name="btnCart8" 
        Grid.Row="3" 
        Grid.Column="1" 
        Tag="8" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <!-- Fila 5: Botón 9 y Botón 10 -->
                                    <Button x:Name="btnCart9" 
        Grid.Row="4" 
        Grid.Column="0" 
        Tag="9" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>

                                    <Button x:Name="btnCart10" 
        Grid.Row="4" 
        Grid.Column="1" 
        Tag="10" 
        Click="CartButton_Click"
        Background="#0f3460" 
        Foreground="White" 
        BorderThickness="0" 
        Height="60" 
        Margin="5" Padding="5" 
        FontSize="10" 
        FontWeight="Normal"
        HorizontalContentAlignment="Center" 
        VerticalContentAlignment="Center"/>
                                </Grid>
                        </ScrollViewer>

                        <StackPanel Grid.Row="2" 
                                        Margin="0,10,0,0">
                            <CheckBox x:Name="chkFadeMix" 
                                          Content="🔀 Fade Mix" 
                                          Foreground="{StaticResource TextBrush}" 
                                          Margin="0,0,0,5" FontSize="11"/>
                            <Slider x:Name="sliderFade" 
                                        Minimum="0" 
                                        Maximum="100" 
                                        Value="50" 
                                        Background="#3a3a5a" 
                                        Foreground="{StaticResource AccentBrush}"/>
                            <TextBlock Text="Fade: 2.5s" 
                                           FontSize="10" 
                                           Foreground="{StaticResource TextMutedBrush}" 
                                           HorizontalAlignment="Center"/>
                        </StackPanel>
                    </Grid>
                </TabItem>

                <!-- TAB 2: Comerciales -->
                <TabItem Header="📢 Programación">
                    <Grid Margin="10">
                        <Grid.RowDefinitions>
                            <RowDefinition Height="Auto"/>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="Auto"/>
                        </Grid.RowDefinitions>

                        <StackPanel Orientation="Horizontal" Margin="0,0,0,10">
                            <Button x:Name="btnAddEvent" 
                                        Content="➕ Nuevo Evento" 
                                        Background="#e94560" 
                                        Foreground="White" 
                                        BorderThickness="0" 
                                        Padding="8,4" 
                                        Cursor="Hand" 
                                        Margin="0,0,5,0"
                                        FontSize="11"
                                        Click="BtnAddEvent_Click"/>
                            <Button x:Name="btnEditEvent" 
                                        Content="✏️ Editar" 
                                        Background="#252542" 
                                        Foreground="White" 
                                        BorderThickness="0" 
                                        Padding="8,4" 
                                        Cursor="Hand" 
                                        Margin="0,0,5,0"
                                        IsEnabled="False"
                                        FontSize="11"
                                        Click="BtnEditEvent_Click"/>
                            <Button x:Name="btnDeleteEvent" 
                                        Content="🗑️ Eliminar" 
                                        Background="#252542" 
                                        Foreground="#ff6b6b" 
                                        BorderThickness="0" 
                                        Padding="8,4" 
                                        Cursor="Hand"
                                        IsEnabled="False"
                                        FontSize="11"
                                        Click="BtnDeleteEvent_Click"/>
                        </StackPanel>

                        <ListView x:Name="lvEvents" 
                                        Grid.Row="1" 
                                        Background="Transparent" 
                                        BorderThickness="0" 
                                        Foreground="White"
                                        SelectionChanged="LvEvents_SelectionChanged">
                            <ListView.ItemTemplate>
                                <DataTemplate>
                                    <Border Background="#252542" Margin="0,2" Padding="8" CornerRadius="6">
                                        <Grid>
                                            <Grid.ColumnDefinitions>
                                                <ColumnDefinition Width="Auto"/>
                                                <ColumnDefinition Width="*"/>
                                                <ColumnDefinition Width="Auto"/>
                                            </Grid.ColumnDefinitions>

                                            <Border Grid.Column="0" Background="#00d9a5" CornerRadius="4" Padding="6,3" Margin="0,0,10,0">
                                                <TextBlock Text="{Binding StartTime, StringFormat='HH:mm'}" FontWeight="Bold" Foreground="#1a1a2e" FontSize="10"/>
                                            </Border>

                                            <StackPanel Grid.Column="1">
                                                <TextBlock Text="{Binding Name}" FontWeight="SemiBold" Foreground="White" FontSize="12"/>
                                                <TextBlock Text="{Binding DisplayInfo}" FontSize="9" Foreground="#a0a0a0"/>
                                            </StackPanel>

                                            <StackPanel Grid.Column="2" Orientation="Horizontal">
                                                <Border Background="#e94560" CornerRadius="4" Padding="6,3" 
                                                            Visibility="{Binding IsActive, Converter={StaticResource BoolToVisibility}}">
                                                    <TextBlock Text="Activo" FontSize="9" Foreground="White"/>
                                                </Border>
                                            </StackPanel>
                                        </Grid>
                                    </Border>
                                </DataTemplate>
                            </ListView.ItemTemplate>
                        </ListView>

                        <Button x:Name="btnTestEvent" 
                Grid.Row="2" 
                Content="🎬 Probar Evento" 
                Background="#0f3460" 
                Foreground="White" 
                BorderThickness="0" 
                Padding="6,3" 
                Cursor="Hand" 
                FontSize="11" 
                Margin="0,10,0,0"
                IsEnabled="False" 
                Click="BtnTestEvent_Click"/>
                    </Grid>
                </TabItem>

                <!-- TAB 3: RDS -->
                <TabItem Header="📡 RDS">
                    <Grid Margin="10">
                        <StackPanel>
                            <TextBlock Text="Texto RDS:" 
                                           FontWeight="SemiBold" 
                                           Margin="0,0,0,5" 
                                           FontSize="11"/>
                            <TextBox x:Name="txtRDS" 
                                         Text="LUNIMAR FM • ---" 
                                         Background="#252542" 
                                         Foreground="White" 
                                         BorderThickness="0" 
                                         Padding="8" 
                                         Margin="0,0,0,10" 
                                         FontSize="11"/>
                            <TextBlock Text="Programación:" 
                                           FontWeight="SemiBold" 
                                           Margin="0,0,0,5" 
                                           FontSize="11"/>
                            <ListBox Background="#252542" 
                                         BorderThickness="0" 
                                         Height="150" 
                                         Foreground="{StaticResource TextBrush}" 
                                         FontSize="10">
                                <ListBoxItem>14:00 - LUNIMAR FM</ListBoxItem>
                                <ListBoxItem>14:05 - The Weeknd - Blinding Lights</ListBoxItem>
                                <ListBoxItem Background="#2a2a4a">14:10 - 📢 PROMO VERANO</ListBoxItem>
                                <ListBoxItem>14:12 - Olivia Rodrigo - Good 4 U</ListBoxItem>
                            </ListBox>
                            <Button Content="🔄 Actualizar" 
                                        Background="#252542" 
                                        Foreground="White" 
                                        Padding="10,5" 
                                        BorderThickness="0" 
                                        Margin="0,10,0,0" 
                                        Cursor="Hand" 
                                        HorizontalAlignment="Stretch" 
                                        FontSize="11"/>
                        </StackPanel>
                    </Grid>
                </TabItem>

                <!-- TAB 4: Reportes -->
                <TabItem Header="📊 Reportes">
                    <Grid Margin="10">
                        <StackPanel>
                            <ComboBox Background="#252542" 
                                          Foreground="Black" 
                                          BorderThickness="0" 
                                          Padding="8" 
                                          Margin="0,0,0,10" 
                                          FontSize="11">
                                <ComboBoxItem IsSelected="True">📋 Log Hoy</ComboBoxItem>
                                <ComboBoxItem>📈 Stats Semanal</ComboBoxItem>
                            </ComboBox>
                            <Border Background="#252542" 
                                        Padding="10" 
                                        Height="200">
                                <ScrollViewer VerticalScrollBarVisibility="Auto">
                                    <StackPanel>
                                        <TextBlock Text="14:30 • Dua Lipa • Levitating • Pop" 
                                                       FontSize="10"/>
                                        <TextBlock Text="14:33 • Jingle • Top of Hour • Imaging" 
                                                       FontSize="10"/>
                                        <TextBlock Text="14:34 • The Weeknd • Blinding Lights • Pop" 
                                                       FontSize="10" 
                                                       Foreground="{StaticResource SuccessBrush}"/>
                                        <TextBlock Text="14:37 • Olivia Rodrigo • Good 4 U • Pop-Rock" 
                                                       FontSize="10"/>
                                    </StackPanel>
                                </ScrollViewer>
                            </Border>
                            <Grid Margin="0,10,0,0">
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="*"/>
                                    <ColumnDefinition Width="*"/>
                                </Grid.ColumnDefinitions>
                                <Button Content="🖨️ Imprimir" 
                                            Background="#252542" 
                                            Foreground="White" 
                                            Padding="8,4" 
                                            BorderThickness="0" 
                                            Margin="0,0,5,0" 
                                            Cursor="Hand" 
                                            FontSize="11"/>
                                <Button Grid.Column="1" 
                                            Content="📤 PDF" 
                                            Style="{StaticResource PrimaryButton}" 
                                            Padding="8,4" 
                                            Cursor="Hand" 
                                            FontSize="11"/>
                            </Grid>
                        </StackPanel>
                    </Grid>
                </TabItem>
            </TabControl>
        </Border>
    </Grid>

    <!-- ============ PLAYER CONTROLS ============ -->
    <Border Grid.Row="3" 
                Background="{StaticResource SecondaryBrush}" 
                BorderBrush="#3a3a5a" 
                BorderThickness="0,1,0,0" 
                Padding="15,10">
        <ScrollViewer HorizontalScrollBarVisibility="Auto" 
                          VerticalScrollBarVisibility="Disabled">
            <Grid MinWidth="700">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto"/>
                    <ColumnDefinition Width="*"/>
                    <ColumnDefinition Width="Auto"/>
                    <ColumnDefinition Width="Auto"/>
                </Grid.ColumnDefinitions>

                <StackPanel Orientation="Horizontal" 
                                VerticalAlignment="Center">
                    <Button Content="⏮️" 
                                Width="40" 
                                Height="40" 
                                Background="Transparent" 
                                BorderThickness="0" 
                                Foreground="White" 
                                FontSize="18" 
                                Cursor="Hand" 
                                Click="BtnPrev_Click"/>
                    <Button x:Name="btnPlayPause" 
                                Content="▶️" 
                                Width="50" 
                                Height="50" 
                                Background="{StaticResource AccentBrush}" 
                                BorderThickness="0" 
                                Foreground="White" 
                                FontSize="20" Cursor="Hand" 
                                Margin="5,0" 
                                Click="BtnPlayPause_Click"/>
                    <Button Content="⏭️" 
                                Width="40" 
                                Height="40" 
                                Background="Transparent" 
                                BorderThickness="0" 
                                Foreground="White" 
                                FontSize="18" 
                                Cursor="Hand" 
                                Click="BtnNext_Click"/>
                    <Button Content="⏹️" 
                                Width="40" 
                                Height="40" 
                                Background="Transparent" 
                                BorderThickness="0" 
                                Foreground="#ff6b6b" 
                                FontSize="18" 
                                Cursor="Hand" 
                                Margin="10,0,0,0" 
                                Click="BtnStop_Click"/>
                </StackPanel>

                <StackPanel Grid.Column="1" 
                                Orientation="Horizontal" 
                                VerticalAlignment="Center" 
                                Margin="20,0">
                    <TextBlock Text="🔊" 
                                   VerticalAlignment="Center" 
                                   Margin="0,0,5,0"/>
                    <Slider x:Name="volumeSlider" 
                                Width="150" 
                                Minimum="0" 
                                Maximum="100" 
                                Value="100" 
                                Background="#3a3a5a" 
                                Foreground="{StaticResource TextBrush}" 
                                VerticalAlignment="Center" 
                                ValueChanged="VolumeSlider_ValueChanged"/>
                    <TextBlock x:Name="txtVolume" 
                                   Text="100%" 
                                   Width="40" 
                                   Foreground="{StaticResource TextMutedBrush}" 
                                   VerticalAlignment="Center" 
                                   Margin="5,0"/>
                    <Separator Width="1" 
                                   Background="#3a3a5a" 
                                   Margin="10,5"/>
                    <Button x:Name="btnMixer" 
                                Content="🎚️ Mezclador" 
                                Background="#252542" 
                                Foreground="White" 
                                BorderThickness="0" 
                                Padding="8,4" 
                                Cursor="Hand" 
                                FontSize="11" 
                                Margin="5,0,0,0" 
                                Click="BtnMixer_Click"/>
                    <Separator Width="1" 
                                Background="#3a3a5a" 
                                Margin="2,5"/>
                    <Button x:Name="btnEqMaster"  
                                Content="🎚️ EQ" 
                                Background="#252542" 
                                Foreground="White" 
                                Padding="8,4" 
                                BorderThickness="0" 
                                Margin="5,0" 
                                Cursor="Hand" 
                                FontSize="11"
                                Click="btnEqMaster_Click"/>
                    <Button Content="🔧 Comp" 
                                Background="#252542" 
                                Foreground="White" 
                                Padding="8,4" 
                                BorderThickness="0" 
                                Margin="5,0" 
                                Cursor="Hand" 
                                FontSize="11"
                                Click="BtnCompressor_Click"/>
                    <CheckBox Content="🔄 Crossfade" 
                                  IsChecked="True" 
                                  Foreground="{StaticResource TextBrush}" 
                                  Margin="15,0,0,0" 
                                  FontSize="11"/>
                </StackPanel>

                <StackPanel Grid.Column="2" Orientation="Horizontal" VerticalAlignment="Center" Margin="0,0,20,0">
                    <ToggleButton x:Name="btnMic" Content="🎤 MIC" Width="70" Background="#252542" Foreground="White" BorderThickness="1" BorderBrush="#3a3a5a" Padding="5" Cursor="Hand" FontSize="11"/>
                    <ToggleButton x:Name="btnLine" Content="📡 LINE" Width="70" Background="#252542" Foreground="White" BorderThickness="1" BorderBrush="#3a3a5a" Padding="5" Margin="5,0,0,0" Cursor="Hand" FontSize="11"/>
                </StackPanel>

                <StackPanel Grid.Column="3" Orientation="Horizontal" VerticalAlignment="Center">
                    <Border Background="#00d9a5" Padding="8,4">
                        <TextBlock Text="🔴 EN VIVO" FontWeight="Bold" FontSize="11" Foreground="#1a1a2e"/>
                    </Border>
                    <TextBlock Text="• 128kbps • 45" Foreground="{StaticResource TextMutedBrush}" Margin="10,0,0,0" VerticalAlignment="Center" FontSize="11"/>
                </StackPanel>
            </Grid>
        </ScrollViewer>
    </Border>

    <!-- ============ STATUS BAR ============ -->
    <Border Grid.Row="4" Background="{StaticResource PrimaryBrush}" BorderBrush="#3a3a5a" BorderThickness="0,1,0,0" Padding="10,5">
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="*"/>
                <ColumnDefinition Width="Auto"/>
            </Grid.ColumnDefinitions>
            <TextBlock x:Name="txtStatus" Text="✅ Sistema estable • 🎵 Auto: Activo • 📡 Streaming: OK" 
                           Foreground="{StaticResource TextMutedBrush}" FontSize="11" TextTrimming="CharacterEllipsis"/>
            <StackPanel Grid.Column="1" Orientation="Horizontal">
                <Button Content="⚙️" ToolTip="Configuración" Background="Transparent" Foreground="{StaticResource TextMutedBrush}" BorderThickness="0" Padding="5,2" Cursor="Hand" FontSize="11"/>
                <Button Content="❓" ToolTip="Ayuda" Background="Transparent" Foreground="{StaticResource TextMutedBrush}" BorderThickness="0" Padding="5,2" Cursor="Hand" FontSize="11" Margin="10,0,0,0"/>
                <Button x:Name="btnPanic" Content="🚨" ToolTip="Panic - Detener todo" Background="#ff6b6b" Foreground="White" BorderThickness="0" Padding="8,4" Cursor="Hand" FontSize="11" Margin="10,0,0,0" Click="BtnPanic_Click"/>
            </StackPanel>
        </Grid>
    </Border>
</Grid>
</Window>
