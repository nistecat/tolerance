// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © layth7ussein

//@version=5
indicator("Tolerance")

src = input(ohlc4, "Source")
len = input.int(50, "Length")
longLen = input.int(20, "Long MA length")
shortLen = input.int(9, "Short MA length")

tol = src/ta.sma(src, len)-1
tolMAlong = ta.sma(tol, longLen)
tolMAshort = ta.sma(tol, shortLen)

plot(tol, color=color.blue)
plot(tolMAlong, color=color.yellow)
plot(tolMAshort, color=color.red)
