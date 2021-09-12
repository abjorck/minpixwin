# minpixwin
minimize effort to render a pixel array to screen    

very tiny wrapping of the neat `winit` crate 

### example use

add 
`resolver = "2"` to your Cargo.toml 

draw a red rectangle

    use minpixwin::Screen;

    Screen::new(100, 100, move |buf| {
        for (index, pixel) in buf.chunks_exact_mut(4).enumerate() {
            let p = [255u8, 0u8, 0u8, 255u8];
            pixel.copy_from_slice(&p);
        };
    });

TODO: this may not work on your platform, and assumes the default texture format winit creates is 32bit rgba, etc. ymmv
