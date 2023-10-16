# Adding SfTextInputLayout reference
You can add SfTextInputLayout reference using one of the following methods:

## Method 1: Adding SfTextInputLayout reference from nuget.org

Syncfusion Xamarin components are available in nuget.org. To add SfTextInputLayout to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Xamarin.Core, and then install it.


## Method 2: Adding SfTextInputLayout reference from toolbox

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the Xamarin Text Input Layout (SfTextInputLayout) control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to Toolbox.

## Method 3: Adding SfTextInputLayout assemblies manually from the installed location

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

# Initializing text input layout
Import the SfTextInputLayout control namespace in respective page as demonstrated in the following code sample.

**[XAML]**
```
xmlns:inputLayout="clr-namespace:Syncfusion.XForms.TextInputLayout;assembly=Syncfusion.Core.XForms"
```
**[C#]**
```
using Syncfusion.XForms.TextInputLayout;
```
Add any input view control such as Entry, Editor, SfNumericTextBox, SfNumericUpDown, SfMaskedEdit, SfAutoComplete, SfComboBox, Picker,DatePicker or TimePicker and add hint label (floating label).

**[XAML]**
```
<inputLayout:SfTextInputLayout>
   <Entry />
</inputLayout:SfTextInputLayout>
```
**[C#]**
```
var inputLayout = new SfTextInputLayout();
inputLayout.InputView = new Entry();
```
# How to validate with required verification in text input layout in Xamarin.Forms
we are going to highlight the inputview when the user provided input is empty using the HasError  and ErrorText property in TextInputLayout.

**[XAML]**

```
<StackLayout HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand" Margin="15">
        <inputLayout:SfTextInputLayout Hint="Email" 
                                       x:Name="emailField"
                                       ErrorColor="Red" 
                                       FocusedColor="Blue"
                                       ContainerType="Outlined">
            <inputLayout:SfTextInputLayout.Triggers>
                <DataTrigger TargetType="inputLayout:SfTextInputLayout" 
                             Binding="{Binding Source={x:Reference emailentry},Path=Text.Length}" 
                             Value="0">
                    <Setter Property="HasError" Value="True"/>
                    <Setter Property="ErrorText" Value="Email is empty"/>
                </DataTrigger>
            </inputLayout:SfTextInputLayout.Triggers>
            <Entry x:Name="emailentry" />
        </inputLayout:SfTextInputLayout>

        <inputLayout:SfTextInputLayout Hint="Password" 
                                       x:Name="passwordField"
                                       ErrorColor="Red"    
                                       FocusedColor="Blue"
                                       ContainerType="Outlined"                                                
                                       EnablePasswordVisibilityToggle="true">
            <inputLayout:SfTextInputLayout.Triggers>
                <DataTrigger TargetType="inputLayout:SfTextInputLayout" 
                             Binding="{Binding Source={x:Reference pwdentry},Path=Text.Length}" 
                             Value="0">
                    <Setter Property="HasError" Value="True"/>
                    <Setter Property="ErrorText" Value="Password is empty"/>
                </DataTrigger>
            </inputLayout:SfTextInputLayout.Triggers>
            <Entry x:Name="pwdentry" />
        </inputLayout:SfTextInputLayout>

        <Button Text="Next" BackgroundColor="Black" TextColor="White" 
                WidthRequest="100" HorizontalOptions="Center"/>
    </StackLayout> 
```
## How to run this application?

To run this application, you need to first clone the How-to-validate-with-required-verification-in-text-input-layout-in-Xamarin.Forms repository and then open it in Visual Studio 2022. Now, simply build and run your project to view the output.

## <a name="troubleshooting"></a>Troubleshooting ##
### Path too long exception
If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

## License

Syncfusion has no liability for any damage or consequence that may arise by using or viewing the samples. The samples are for demonstrative purposes, and if you choose to use or access the samples, you agree to not hold Syncfusion liable, in any form, for any damage that is related to use, for accessing, or viewing the samples. By accessing, viewing, or seeing the samples, you acknowledge and agree Syncfusion’s samples will not allow you seek injunctive relief in any form for any claim related to the sample. If you do not agree to this, do not view, access, utilize, or otherwise do anything with Syncfusion’s samples.