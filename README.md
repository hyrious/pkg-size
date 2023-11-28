# :package: <samp> [pkg-size](https://hyrious.me/pkg-size)</samp>

Yet another [pkg-size](https://pkg-size.dev/) but this one only checks metadata.

## Usage

Goto
<samp><a href="https://hyrious.me/pkg-size/#esbuild">https://hyrious.me/pkg-size/#{package-name}</a></samp>
and see the size report.

**Examples**

- https://hyrious.me/pkg-size/#lodash
- https://hyrious.me/pkg-size/#esbuild (see package.json "os", "cpu" works)

## Why

There are several tools before, [bundlephobia](https://bundlephobia.com/) runs
webpack on a package to see its packed size, [bundlejs](https://bundlejs.com/)
runs esbuild instead, [pkg-size](https://pkg-size.dev/) runs real npm on web
container to see its installed size.

However, the web container still needs some time to warm up, and downloading the
package also takes time. I want to see the result as fast as possible (no
accuracy is ok), so I wrote another one.

## How it works

The registry will tell you a package's <q>unpackedSize</q>, which is what you
see on `npmjs.com`. This tool accumulates all dependencies' unpacked size to
give you the final number.

## License

MIT @ [hyrious](https://github.com/hyrious)
