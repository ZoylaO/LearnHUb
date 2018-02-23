# LearnHUb
A learning Environment 
HI ITZEL!!!
Helloooo
This is Eric. I am Eric.
it meeee
using Android.App;
using Android.Widget;
using Android.OS;

using System.Net;
using System.Net.Http;
using System.IO;
using Android.Graphics;

namespace acmApp1
{
[Activity(Label = “acmApp1” , MainLauncher = true, Icon = “@mimap/icon”)]
public class MainActivity : Activity
{
int count = 1;

protected override void OnCreate(Bundle savedInstanceState)
{
base.OnCreate(savedInstanceState);

SetContentView(Resource.Layout.Main);
HttpClient client = new HttpClient();
string url = “https://i.imgur.com/Z1UDqUp.jpg”;
Stream stream = null;
Bitmap bmp1;
ImageView img1;
Button button1;

img1 = FindViewById<ImageView>(Resource.Id.imageView1);
button1 = FindViewById<Button>(Resource.Id.button1);


stream = client.GetStreamAsync(url).Result;
bmp1 = BitmapFactory.DecodeStream(stream);

img1.SetImageBitmap(bmp1);

Button button = FindViewById<Button>(Resource.Id.myButton);

button.Click += delegate { button.Text = string.Format(“{0} clicks!”, count++);};
button1.Click += delegate

{
img1.RotationX = img1.RotationX + 20;
};
}
           }
} 
