cat > README.md <<'EOF'
# HyperFrames M1 Render Shift Reproduction

This is a minimal reproduction for a HyperFrames CLI render issue on Apple Silicon M1.

## Issue

On Apple Silicon M1, `npx hyperframes render` produces a vertical compositor/layout shift in the rendered MP4 after approximately 9–12 seconds, and again at later timeline points.

The same composition:
- previews correctly in HyperFrames Studio when Studio is available
- renders correctly on an Intel Mac
- shifts vertically only in the CLI-rendered MP4 on M1

## Environment with issue

- Machine: MacBook Air M1, 8GB unified memory
- HyperFrames: 0.6.4
- Node.js: v25.9.0 and/or Node 22
- FFmpeg: 8.1
- Chrome: system Chrome
- Command: `npx hyperframes render --output output.mp4`

## Reproduction steps

```bash
npm install
npx hyperframes doctor
npx hyperframes render --output output-m1.mp4
