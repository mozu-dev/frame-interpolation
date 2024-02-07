# frame-interpolation
I have tested frame interpolation using [sd-webui-deforum](https://github.com/deforum-art/sd-webui-deforum). This is the log for the experiment.

## Machine specification
```
Processor: 1.1 GHz Quad-Core Intel Core i5
Graphics: Intel Iris Plus Graphics 1536 MB
Memory: 16 GB 3733 MHz LPDDR4X
```

## Testing
### Installation
- I cloned [stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui):
```
$ git clone git@github.com:AUTOMATIC1111/stable-diffusion-webui.git
```
- I downloaded the model data from [here](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon#downloading-stable-diffusion-models) and placed it in the `stable-diffusion-webui/models/Stable-diffusion`:
```
$ mv ~/Downloads/sd-v1-4.ckpt stable-diffusion-webui/models/Stable-diffusion
```
- I launched the WebUI:
```
$ cd stable-diffusion-webui
```
```
$ ./webui.sh --precision full --no-half
```
- I installed *deforum* on the WebUI referring to [this article](https://romptn.com/article/17991#toc2).
- I installed [sd-webui-controlnet](https://github.com/Mikubill/sd-webui-controlnet) on the WebUI referring to [this article](https://romptn.com/article/7868#toc5).
### Applying
- I prepared the video, which has a frame rate of 2 fps and a duration of 1 second, for frame interpolation:
![input](https://github.com/mozu-dev/frame-interpolation/blob/main/images/input.gif)
- I applied frame interpolation to the video by referring to [this article](https://note.com/gentle_murre488/n/nd607621751f1), setting `RIFE v4.6` for the engine and `10` for the Interp X.
- I got a frame-interpolated video:
![output](https://github.com/mozu-dev/frame-interpolation/blob/main/images/output_RIFE_x10.gif)

## References
- [Stable Diffusionの拡張機能『Deforum』の使い方！アニメーション動画を作ろう
](https://romptn.com/article/17991)
- [MacでStableDiffusionWebUIを試す](https://zenn.dev/ymmt1089/scraps/02f4c6ebc49b80)
- [Deforumで使用出来るFrame interpolateについて試してみた](https://note.com/gentle_murre488/n/nd607621751f1)