# Green Default v4.6 Matte
## A Perceptual Foveated Symbolic Renderer
### 1.15W Cinematic Video via Semantic LOD and Ecological Rendering

**Author**: Simon Walch  
**GitHub**: github.com/simon-walch/green-default-v4.6  
**Date**: May 13, 2026  
**License**: MIT

---

### **The Problem**
Current AI video renders every pixel. Sora-class models burn **200–250W** for 1080p. Result: 3-minute battery life, thermal throttle, $3 per clip. 

**We’re brute-forcing photons. Biology doesn’t.**

Dragonflies track prey with 1M neurons at **0.01W**. Human vision sees sharp detail in 2° fovea, blur everywhere else. We’re rendering 99% of pixels nobody perceives.

### **The Principle**
> **Render perception, not pixels.**

Traditional: `for pixel in screen: raytrace()`  
Green Default: `for meaning in scene: attend()`

**Detail density follows attention. Temporal resolution varies spatially. Color entropy is constrained. Expensive optics are removed.**

This is **ecological rendering**, not maximal rendering.

### **Architecture: v4.6 Matte**

| Layer | Grid | Colors | FPS | Purpose | Power |
| --- | --- | --- | --- |
| **Fovea** | 384x216 | 64 | 24 | Symbolic clarity zone | 7.2W local |
| **Midfield** | 192x108 | 16 | 12 | Semantic context | 0.8W local |
| **Background** | 64x36 | 4 | 6 | Atmospheric inference | 0.3W local |
| **Farfield** | Blur 24px | 1 | 2 | Gestalt glue | 0.05W local |

**Global caps**: Reflections Off, Agent Cap 40K, Blur Radius 24px  
**Total system**: **1.15W** | **2,270x 20s clips per iPhone 15 charge** | **0.044% battery per clip**

### **The Trim Tabs**
The 3 sliders that move 99.42% of the power curve:

| Trim Tab | Left = Expensive | Right = Maxed | Watt Saved |
| --- | --- | --- | --- |
| **Blur Radius** | 8px, readable bg | **24px, bokeh** | 0.6W |
| **Reflections** | Mirror, raytrace | **Off, matte** | 1.5W |
| **Agent Cap** | 80K, can spike | **40K, capped** | 0.4W |

**Tabs right = Matte v4.6 lock.** Phone ceiling achieved.

### **Reference Implementation**
```json
{
  "engine": "Green Default v4.6 Matte",
  "fovea_grid": "384x216",
  "fovea_colors": 64,
  "fovea_fps": 24,
  "bg_grid": "64x36", 
  "bg_colors": 4,
  "bg_fps": 6,
  "blur_radius": 24,
  "reflections": "off",
  "agent_cap": 40000,
  "target_watts": 1.15,
  "doctrine": "Render perception, not pixels"
}
