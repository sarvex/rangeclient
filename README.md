# rangeclient synopsis


    rangehost = ARGV.shift
    rangearg = ARGV.shift

    # Create range object for communication with ranged
    r = Range::Client.new({:host => rangehost})

    # use ranged to expand the range expression into an Array
    # "foo10..12" => [ foo10, foo11, foo12 ] OR %foo => [ foo10, foo11, foo12 ]
    hosts =  r.expand(rangearg)

    # use ranged to compress the array of hostnames into a range expression
    # [ foo10, foo11, foo12 ] => "foo10..12"
    range_exp = r.compress(hosts)

Imported from [https://github.com/square/prodeng](https://github.com/square/prodeng/commit/524dce7d1e81c347129c45491a107c690a071abf).
