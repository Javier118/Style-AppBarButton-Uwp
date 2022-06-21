# Style-AppBarButton-Uwp

<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

    <Style TargetType="AppBarButton" x:Key="AppBarButtonCustomStyle">
        <Setter  Property="Background" Value="Transparent"/>
        <Setter Property="Foreground" Value="Black"/>
        <Setter Property="CornerRadius" Value="5,5,5,5"/>
        <Setter Property="Width" Value="160"/>
        <Setter Property="Height" Value="50"/>
        <Setter Property="BorderBrush" Value="Transparent"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="AppBarButton">
                    <Grid x:Name="RootGrid">
                        
                        <VisualStateManager.VisualStateGroups>
                            <VisualStateGroup x:Name="CommonStates">
                                <VisualState x:Name="Normal">
                                    <Storyboard>
                                        <PointerUpThemeAnimation Storyboard.TargetName="RootGrid"/>
                                    </Storyboard>
                                    
                                </VisualState>
                                <VisualState x:Name="PointerOver">
                            <Storyboard>
                                        <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background"  Storyboard.TargetName="RootGrid">
                                            <DiscreteObjectKeyFrame KeyTime="0" Value="#e6e6e6"/>
                                        </ObjectAnimationUsingKeyFrames>
                                        <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Foreground"  Storyboard.TargetName="TextLabel">
                                            <DiscreteObjectKeyFrame KeyTime="0"  Value="Black"/>
                                        </ObjectAnimationUsingKeyFrames>
                                        <PointerDownThemeAnimation Storyboard.TargetName="RootGrid"/>
                                    </Storyboard>
                        </VisualState>
                                <VisualState x:Name="Pressed">
                                    <Storyboard>
                                        <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background"  Storyboard.TargetName="RootGrid">
                                            <DiscreteObjectKeyFrame KeyTime="0" Value="#cccccc;"/>
                                        </ObjectAnimationUsingKeyFrames>
                                        <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Foreground"  Storyboard.TargetName="TextLabel">
                                            <DiscreteObjectKeyFrame KeyTime="0"  Value="Black"/>
                                        </ObjectAnimationUsingKeyFrames>
                                        <PointerDownThemeAnimation Storyboard.TargetName="RootGrid"/>
                                    </Storyboard>
                                   
                                </VisualState>
                                <VisualState x:Name="Disabled">
                                    <Storyboard>
                                        <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Background"  Storyboard.TargetName="RootGrid">
                                            <DiscreteObjectKeyFrame KeyTime="0" Value="White;"/>
                                        </ObjectAnimationUsingKeyFrames>
                                        <ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Foreground"  Storyboard.TargetName="TextLabel">
                                            <DiscreteObjectKeyFrame KeyTime="0"  Value="Black"/>
                                        </ObjectAnimationUsingKeyFrames>
                                        
                                    </Storyboard>
                                    
                                </VisualState>
                        </VisualStateGroup>
                  </VisualStateManager.VisualStateGroups>

                        

                        <ContentPresenter x:Name="Content"
                                              Height="{TemplateBinding Height}"
                                              Width="{TemplateBinding Width}"
                                              Margin="-65,0,0,0"
                                              CornerRadius="{TemplateBinding CornerRadius}"
                                             
                                              Content="{TemplateBinding Icon}"
                                              Foreground="{TemplateBinding Foreground}"/>

                            <TextBlock x:Name="TextLabel"
                                       Grid.Row="0"
                                       Text="{TemplateBinding Label}"
                                       Foreground="{TemplateBinding Foreground}"
                                       Margin="60,20,0,0"/>

                        
                    </Grid>
                </ControlTemplate>
            </Setter.Value>
        </Setter>

    </Style>
    
</ResourceDictionary>
