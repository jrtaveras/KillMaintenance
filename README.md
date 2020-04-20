# KillMaintenance
KillMaintenance are a set of CodeSmith templates (https://www.codesmithtools.com/)  for fast development, 
generating Model,Interface,Presenter and the user interface of the user control from the table structures in the database.

## Some of the dependencies it has:
1. They are Wisej https://wisej.com/ (which is a Framework for the development of business Web Applications),Wisej.Ext.MaterialDesign. 2. SmartXLS http://www.smartxls.com/ (Library to export data to excel), Entityframework 6.4 (ORM), 
3. NInject (Dependency Manager) http://www.ninject.org/ and SqlServer. 
4. The MVP design pattern is implemented (https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter) and Dependency Injection.

## Features
Multitenance, MultiLanguage, Automatic Validations obtained from the definition of table structure in the database, CRUD and Automatic Search, scheme for tests (Unit Test of presenter)

## Restrictions
All tables must have a primary key Called Id(Identity) that can be Int or BigInt, all the tables must have the following fields: Creado (Varchar), FechaCreado (DateTime), Modificado (Varchar) and FechaModificado (DateTime)

## Screen of CodeSmith running KillMaintenance
![Screen of CodeSmith running KillMaintenance](/assets/CodeSmith.PNG) (https://www.youtube.com/watch?v=Y8rvl_QEhXk)

## Screen in Visual Studio showing an example of  Maintenance generated
![Screen en Visual Studio showing an example of  Maintenance generated](/assets/Pantallagenerada.PNG)
![Customer](/assets/Customer.png)
## Main page code
```

using BusinessObjects;
using BusinessObjects.Interfaces;
using BusinessObjects.Repository;
using Common;
using Common.Helpers;
using CommonUserControls;
using YourApp.Factory;
using YourApp.Interfaces;
using System;
using System.Drawing;
using System.Resources;
using System.Threading;
using Wisej.Web;
using Wisej.Web.Ext.NavigationBar;
using System.Globalization;
namespace YourApp
{
    public partial class Page1 : Page
    {
        private readonly IContext _context;
        private readonly IFactoryUserControls _factory;
        private RegionalizationHelper _regionalizationHelper;

        public Page1()
        {
            InitializeComponent();
            
            
            _context = new MyContext("TestOrlando");
            _context.LocalizationName = "en-US";
            _context.UserName = "admin";
            var culture = new System.Globalization.CultureInfo(_context.LocalizationName);
            Application.CurrentCulture = culture;
            Thread.CurrentThread.CurrentCulture = culture;
            Thread.CurrentThread.CurrentUICulture = culture;
            CultureInfo.DefaultThreadCurrentCulture = culture;
            
            _context.CultureInfo = culture;
            _context.UserName = "admin";
            Resource.Culture = culture;
            ResourceManager resource = Resource.ResourceManager;
            _context.ResourceManager = resource;
            _regionalizationHelper = new RegionalizationHelper(this, _context.ResourceManager,culture);
            _factory = new FactoryUserControlsImps(_context);
            Thread.CurrentThread.CurrentCulture = culture;
            Thread.CurrentThread.CurrentUICulture = culture;


        }
        private void navigationBarMainMenu_ItemClick(object sender, NavigationBarItemClickEventArgs e)
        {
            try
            {
                if (e.Item.Items.Count == 0)
                    addControlsToTab(_factory.GetUserControl(e.Item.Name));
            }
            catch (Exception ex)
            {
                AlertBox.Show(ex.Message, alignment: ContentAlignment.TopLeft, showCloseButton: true, icon: MessageBoxIcon.Error, autoCloseDelay: 10000);
            }

            if (Application.Browser.Device == "Mobile")
                this.navigationBarMainMenu.Visible = false;
        }

        private void addControlsToTab(Common.Controls.UserControlBase userControl)
        {
            if (string.IsNullOrEmpty(userControl.MenuItem))
            {
                return;
            }


            if (tabControlMain.TabPages.ContainsKey(userControl.MenuItem))
            {
                tabControlMain.SelectedTab = tabControlMain.TabPages[userControl.MenuItem];
                return;
            }

            

            if (tabControlMain.TabPages.Count >= 5)
            {
                AlertBox.Show($"{getMessageOpenForm()} {userControl.GetTitle()}, {getMessageCloseForm()}  ", alignment: ContentAlignment.TopLeft, showCloseButton: true);
                return;
            }

            TabPage tabPage = new TabPage(userControl.GetTitle());
            tabPage.Name = userControl.MenuItem;

            userControl.BorderStyle = BorderStyle.None;
            userControl.ScrollBars = ScrollBars.Vertical;
            tabPage.Controls.Add(userControl);
            userControl.Dock = DockStyle.Fill;
            tabPage.ShowCloseButton = true;
            tabControlMain.TabPages.Add(tabPage);
            tabControlMain.SelectedTab = tabPage;
        }

        private string getMessageOpenForm()
        {
            return _context.ResourceManager.GetString(nameof(CommonConstants.MessageOpenForm)) ?? CommonConstants.MessageOpenForm;
        }
        private string getMessageCloseForm()
        {
            return _context.ResourceManager.GetString(nameof(CommonConstants.MessageCloseForm)) ?? CommonConstants.MessageCloseForm;
        }

        private void navigationBar1_ResponsiveProfileChanged(object sender, ResponsiveProfileChangedEventArgs e)
        {
            this.navigationBarMainMenu.CompactView = Application.Browser.ScreenSize.Width < 700;
        }

        private void navigationBar1_TitleClick(object sender, EventArgs e)
        {
            navigationBarMainMenu.CompactView = !navigationBarMainMenu.CompactView;

        }

        
    }
}


```
## License
[MIT](https://choosealicense.com/licenses/mit/)

