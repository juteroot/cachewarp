# CacheWarp

Gem targeted towards providing a solution to verify cache headers for content delivery services like Akamai

## Usage

### Using Ruby Code

Using CacheWarp object

```
    require 'cachewarp'                                 #Require CacheWarp in your file
    request = CacheWarp.new('http://www.akamai.com/')   #Initialize Request Object
    request.fetch                                       #Fetch Request
    request.response_headers                            #Get Response Headers
    request.is_cached?                                  #Verify 'TCP HIT' i.e if Akamai is caching the request
    
```

One Liner

```
    CacheWarp.new("http://www.google.com/").is_cached?  #Returns 'false' since Google does not cache using Akamai
    
```

### Console/CommandLine/Terminal/System Command

Following is an example of non zero exit code. Run the following command on terminal

```
    $ ruby -e 'require "cachewarp"; exit -1 unless CacheWarp.new("http://www.google.com/").is_cached?'
    $ echo $?
    
```

## Installation

Using Bundler

```
    gem 'cachewarp' #Add to Gemfile
    $ bundle        #Install Gem
    
```

Using gem command

```
    $ gem install cachewarp
    
```

##Change Log:

0.0.2

    * Now you can directly perform 'CacheWarp.new('http://www.akamai.com/').is_cached?'

0.0.1

    * Provision to verify TCP HIT in Akamai cache

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Contributors

@juteroot
@bitweft
@codeweft
