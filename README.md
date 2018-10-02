# Stretch Video #

Stretches a video to fill its container, regardless of aspect ratio

## Example ##

    <link rel="import" href="bower_components/stretch-video/stretch-video.html">

    <stretch-video id="sv1" src="video/tc30.mp4">
		<event-point time="2" callback="pause"></event-point>
		<event-point time="8" callback="pause"></event-point>
	</stretch-video>
	<stretch-video id="sv2" src="video/tc30.mp4">
		<event-point time="2" callback="pause"></event-point>
		<event-point time="8" callback="pause"></event-point>
	</stretch-video>
	<script>
		var sv1 = document.querySelector('#sv1');
		var sv2 = document.querySelector('#sv2');

		function pause() {
			sv1.pause();
		}

		sv1.addEventListener('click', function() {
			sv1.play();
		});

		sv1.addEventListener('mirror', function(event) {
			if(typeof event.detail.tag == 'undefined')
				sv2[event.detail.function].apply(sv2, event.detail.arguments.concat(['tag-1']));
		});
	</script>