# react-optics-diagrams

![CI Status](https://github.com/cheminfo/react-optics-diagrams/actions/workflows/nodejs-ts.yml/badge.svg)

React components for displaying optical design diagrams.

Currently the following diagrams are provided:

1. **SpotDiagram** - A single spot diagram for displaying the result of a geometrical ray trace
2. **SpotDiagramGrid** - A grid of spot diagrams, one for each combination of a design's wavelength and field point

## Quickstart

### Installation

```console
npm install react-optics-diagrams
```

### Use

Use the component diagrams like you would any other React component. For example, as a script:

```typescript
// ...
const rayTraceResults: RayTraceResults = data;

const props = {
  rayTraceResults,
  wavelengths: [
    { value: 0.4861, units: 'µm' },
    { value: 0.5876, units: 'µm' },
    { value: 0.6563, units: 'µm' },
  ],
  fieldSpecs: [
    { value: 0.0, units: 'deg', type: 'angle' } as const,
    { value: 5.0, units: 'deg', type: 'angle' } as const,
  ],
};

ReactDOM.createRoot(document.getElementById('app') as HTMLElement).render(
  <React.StrictMode>
    <SpotDiagramsGrid {...props} />
  </React.StrictMode>,
);
```

This will create a grid of spot diagrams that looks like the following, one for each field and wavelength combination.

![A grid of spot diagrams, one for each field and wavelength combination.](/images/spot-diagrams-grid.png)

## Development

### Demo

See the [demo](demo/) folder for examples.

### Common Commands

```console
# Run the demo on the development server
npm run dev

# Run tests
npm run test
```
