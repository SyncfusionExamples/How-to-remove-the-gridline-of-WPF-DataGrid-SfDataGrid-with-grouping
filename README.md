# How to remove the gridline of WPF DataGrid(SfDataGrid) with grouping
## About the sample

This example illustrates how to remove the gridline of DataGrid with grouping

By default, DataGrid having gird lines for each row and column. But we can remove the grid lines for default row by write style for BorderThickness of GridCell. And remove the grid lines for caption row by write style for BorderThickness of GridCaptionSummaryCell and GridIndentCell.

```xml
<Style TargetType="syncfusion:GridCell">
    <Setter Property="BorderThickness" Value="0"/>
</Style>
<Style TargetType="syncfusion:GridIndentCell">
    <Setter Property="BorderThickness" Value="0"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridIndentCell}">
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
<Style TargetType="syncfusion:GridCaptionSummaryCell">
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridCaptionSummaryCell}">
                <Border x:Name="PART_GridCaptionSummaryCellBorder"
                    BorderThickness="0"
                    SnapsToDevicePixels="True">
                    <ContentPresenter Margin="{TemplateBinding Padding}"
                                  HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}"
                                  VerticalAlignment="{TemplateBinding VerticalContentAlignment}"
                                  SnapsToDevicePixels="True" />
                </Border>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
```

## Requirements to run the demo
Visual Studio 2015 and above versions
