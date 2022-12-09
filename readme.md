# 1. WinUI 3 Gallery 코딩

## 1.1 PasswordBox

![1](/img/1.png) ![2](/img/2.png)

비밀번호 입력창으로 체크 박스를 통해 입력 내용을 확인할 수 있는 기능입니다.

## 1.2 Xaml

```xaml
<Grid Padding="10">
        <Grid.RowDefinitions>
            <RowDefinition Height="30" />
            <RowDefinition Height="Auto" />
        </Grid.RowDefinitions>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
        </Grid.ColumnDefinitions>

        <Grid Grid.Row="0">
            <TextBlock><Bold>PasswordBox</Bold></TextBlock>
        </Grid>

        <Grid Grid.Row="1" Background="WhiteSmoke" CornerRadius="8">
            <StackPanel Padding="10" Orientation="Vertical">
                <PasswordBox Name="passworBoxWithRevealmode" Width="250" PasswordRevealMode="Hidden" Padding="10"/>

                <CheckBox Name="revealModeCheckBox" Content="Show password" IsChecked="False" Padding="10"
                      Checked="revealModeCheckBox_Checked" Unchecked="revealModeCheckBox_Unchecked"/>
            </StackPanel>
        </Grid>
    </Grid>
```

체크박스의 Checked와 Unchecked를 통해 패스워드 박스의 상태를 바꿔줍니다.

## 1.3 Cpp

```cpp
using namespace Microsoft::UI::Xaml::Controls;

void winrt::App2::implementation::MainWindow::revealModeCheckBox_Checked(winrt::Windows::Foundation::IInspectable const& sender, winrt::Microsoft::UI::Xaml::RoutedEventArgs const& e)
{
    passworBoxWithRevealmode().PasswordRevealMode(PasswordRevealMode::Visible);
}


void winrt::App2::implementation::MainWindow::revealModeCheckBox_Unchecked(winrt::Windows::Foundation::IInspectable const& sender, winrt::Microsoft::UI::Xaml::RoutedEventArgs const& e)
{
    passworBoxWithRevealmode().PasswordRevealMode(PasswordRevealMode::Hidden);
}
```

체크박스의 상태가 변경되면 패스워드 박스의 PasswordRevealMode()의 값을 Visible와 Hidden으로 바꿔줍니다.

## 2. 영상

