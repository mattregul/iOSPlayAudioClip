# iOSPlayAudioClip
Xamarin - [iOS] How to play an MP3 / WAV using AVAudioPlayer

```csharp
using System;
using AVFoundation;
using Foundation;
using UIKit;

namespace iOSPlayAudioClip
{
	public partial class ViewController : UIViewController
	{

		AVAudioPlayer _player;
		NSError error;

		protected ViewController(IntPtr handle) : base(handle)
		{
			// Note: this .ctor should not contain any initialization logic.
		}

		public override void ViewDidLoad()
		{
			base.ViewDidLoad();


			// WAV File ================================================================
			// Sound from  http://opengameart.org/content/warp-sound-2
			_player = new AVAudioPlayer(NSUrl.FromFilename("wave2.wav"), "wav", out error)
			{
				Volume = 2,
				NumberOfLoops = -1 // Loop Forever
			};
			_player.Play();


			// MP3 File ================================================================
			// MP3 from http://www.stephaniequinn.com/samples.htm
			//_player = new AVAudioPlayer(NSUrl.FromFilename("VivaldiSpringfromFourSeasons.mp3"), "wav", out error)
			//{
			//	Volume = 2,
			//	NumberOfLoops = -1 // Loop Forever
			//};
			//_player.Play();


		}

		public override void DidReceiveMemoryWarning()
		{
			base.DidReceiveMemoryWarning();
			// Release any cached data, images, etc that aren't in use.
		}
	}
}
```
