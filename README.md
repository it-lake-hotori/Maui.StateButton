# Maui.StateButton  [![Nuget](https://img.shields.io/nuget/v/IeuanWalker.Maui.StateButton)](https://www.nuget.org/packages/IeuanWalker.Maui.StateButton) [![Nuget](https://img.shields.io/nuget/dt/IeuanWalker.Maui.StateButton)](https://www.nuget.org/packages/IeuanWalker.Maui.StateButton) 

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FIeuanWalker%2FMaui.StateButton.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FIeuanWalker%2FMaui.StateButton?ref=badge_shield)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/b4823215925c47f7a42b64bc516a6e42)](https://www.codacy.com/gh/IeuanWalker/Maui.StateButton/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=IeuanWalker/Maui.StateButton&amp;utm_campaign=Badge_Grade)

With this control you are able to create any style of button.
This is possible as it acts as a wrapper to your XAML and provides you the events/ commands and properties to bind too.

It's also 100% accessible with each platform seeing/ treating the control as a native button.

The [example page](https://github.com/IeuanWalker/Maui.StateButton/blob/master/Demo/ExamplePage.xaml), has a bunch of different design to showcase the usage -

![Example gif](/Example.gif)

## How to use it?
Install the [NuGet package](https://www.nuget.org/packages/IeuanWalker.StateButton) into your shared project project
```
Install-Package IeuanWalker.StateButton
```

## What can I do with it?
### Properties
| Property | What it does | Extra info |
|---|---|---- |
| State | This changes based on the button state. i.e. `Pressed`, `NotPressed` | Default state is `NotPressed` <br/>  <br/> The binding mode is `OneWayToSource` so it can only be controlled via this control. |

### Events
| Event | What it does |
|---|---|
| Clicked | Triggerd when the button is pressed and released |
| Pressed | Triggerd when the button is pressed |
| Released | Triggerd when the button is released |

### Commands
| Command | What it does |
|---|---|
| ClickedCommand | Triggerd when the button is pressed and released |
| PressedCommand | Triggerd when the button is pressed |
| ReleasedCommand | Triggerd when the button is released |


## How to style the button for different states
Simply add a Trigger to any element and bind it to the `State` property of the button - 
```xaml
<stateButton:StateButton HorizontalOptions="Center">
    <stateButton:StateButton.Content>
        <Frame Padding="20,10" BackgroundColor="Red">
            <Frame.Triggers>
                <DataTrigger Binding="{Binding Source={RelativeSource AncestorType={x:Type stateButton:StateButton}}, Path=State}"
                             TargetType="Frame"
                             Value="Pressed">
                    <Setter Property="BackgroundColor" Value="LightGray" />
                </DataTrigger>
            </Frame.Triggers>
            <Label Text="Test" TextColor="White">
                <Label.Triggers>
                    <DataTrigger Binding="{Binding Source={RelativeSource AncestorType={x:Type stateButton:StateButton}}, Path=State}"
                                 TargetType="Label"
                                 Value="Pressed">
                        <Setter Property="TextColor" Value="Blue" />
                    </DataTrigger>
                </Label.Triggers>
            </Label>
        </Frame>
    </stateButton:StateButton.Content>
</stateButton:StateButton>
```

## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FIeuanWalker%2FMaui.StateButton.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FIeuanWalker%2FMaui.StateButton?ref=badge_large)
