# SparkSL Texel Fetch

Creators porting shaders from [ShaderToy](https://shadertoy.com/) to [SparkSL](https://sparkar.facebook.com/ar-studio/learn/sparksl/sparksl-overview/) often need to convert [texelFetch](https://registry.khronos.org/OpenGL-Refpages/gl4/html/texelFetch.xhtml), which isn't available in SparkSL. 

![screenshot](./spark-texel-fetch.jpg)

## Download

[Download the demo project](https://github.com/positlabs/spark-texel-fetch/archive/refs/heads/master.zip)

## Copypasta

```
/*

  Implementation of texelFetch in SparkSL

*/
export vec4 texelFetch(std::Texture2d tex) {
  vec2 uv = std::getVertexTexCoord();
  vec2 rtSize = std::getRenderTargetSize();
  vec2 texelUV = floor(fragment(uv) * rtSize) / rtSize;
  return tex.sample(texelUV);
}

vec4 main (std::Texture2d tex){
  return texelFetch(tex);
}

```


## Donations

If you used this in client projects, or simply enjoyed making effects with my open-source projects, please consider a donation or sponsorship. One-time donations can be made with PayPal. Subscriptions can be through PayPal or Github Sponsors (click the heart sponsor button at the top of the page).

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YGS69CHAE9EQC&source=url)