![Alt text](/picts/whale2.png?raw=true "pywhale logo")

## Python3 wrapper for whaleclub REST api

PyWhale is a python3 wrapper for [whaleclub.co REST api](http://docs.whaleclub.co/#overview). [Whaleclub.co](https://whaleclub.co/) in addition of offering a demo mode for newcomers, is a great trading exchange platform having one of the best UI and support service I've saw so far. 

PyWhale was created to keep things as simple and intuitive as possible while performing complex requests to REST api. It contains all functions available in [whaleclub.co REST api documentation](http://docs.whaleclub.co/#overview) allowing user to get simultaniously up to 5 markets price, place live or turbo trades, and much more. For better user experience, I've took the liberty to reformat whaleclub.co api functions documentation into functions doc string so one could access all relevants informations directly. PyWhale allows user to easily swith between real/demo mode or BTC/DASH trading simply by changing key function parameter (see usage section).

As far as I know, PyWhale is the only alternative language available if you can't (or just do not want to) use the javascript wrapper in order to interact with whaleclub REST api. PyWhale was created on my own free time, so if you wish to support my work you could start by staring it and either:

* Consider creating an account using my whaleclub's referral link, so you'll get a 30% deposit bonus: 
  * https://whaleclub.co/join/pnI1A
* leave me a tip at:
  * (BTC) 19nm2SJW7zmNcePePW6pyZBh7FMcWZdYeY
  * (DASH) XpdDgn28F3GcwyBjHwb6yKXqJ9nYHbrdup

## Dependencies

* Requests

## Installation
    $ pip3 install requests 
    $ git clone git@github.com:logan169/PyWhale.git
    $ cd PyWhale/app

## How to use it

After creating an account, get your API token from your API Settings panel which is available from the top right menu in your trading dashboard. You get one token for live trading and another for demo trading.

Then complet every following files with their respective api key:

- pywhale/app/BTC_demo_key.txt
- pywhale/app/BTC_real_key.txt
- pywhale/app/DASH_demo_key
- pywhale/app/DASH_real_key

##### Beware to not invert api key, I strongly advise that you verify twice that you've entered the right key in each file.

## Usage

##### Lets start some Whaly stuff:
    
    $ from PyWhale import PyWhale
    $ pw = PyWhale()  
    
![Alt text](/picts/pw.jpg?raw=true "pywhale logo")

##### See all available PyWhale functions:

    $ pw.help()
![Alt text](/picts/help.jpg?raw=true "pywhale logo")

##### See all relevants functions informations and input parameters:

    $ print (pw.function_name.__doc__)
    
![Alt text](/picts/balance.jpg?raw=true "pywhale logo")


##### Switch between real/demo mode & BTC/DASH trading

In PyWhale, you could easily switch between real/demo mode & BTC/DASH trading by either changing default_key attribute value or directly pass key value in function inputs.

###### Possible key values:

- 'BTC_real_key'
- 'BTC_demo_key'
- 'DASH_real_key'
- 'DASH_demo_key'

###### Examples

    $ pw.default_key
    $ pw.default_key = 'DASH_demo_key'
![Alt text](/picts/default_key.jpg?raw=true "pywhale logo")

    $ pw.createNewTurboPosition(market='BTC-USD',position_direction='long',contract_type='5min',size=100000,key='DASH_demo_key')
![Alt text](/picts/passing_key.jpg?raw=true "pywhale logo")
    
    
##### Pease note that if you don't pass a key parameter while calling a function, default.key attribute value will be used.



## License

GNU Lesser General Public

2017 Logan Schwartz logan1691987@gmail.com

pywhale is free software: you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

pywhale is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more details.

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.




    #Start ipython
    $ ipython3
    
    #Import module and create a PyWhale() instance
    $ from PyWhale import PyWhale
    $ pw = PyWhale()    
    
![Alt text](/picts/pw.jpg?raw=true "pywhale logo")

    #Print help
    $ pw.help()
    
![Alt text](/picts/help.jpg?raw=true "pywhale logo")
    
    #Get more information about a function
    $  print (pw.getBalance.__doc__)
    
![Alt text](/picts/balance.jpg?raw=true "pywhale logo")
    
    #Want just ipython output?
    $ pw.verbose = False
![Alt text](/picts/verbose.jpg?raw=true "pywhale logo")

Please note that after creating an PyWhale() instance default.key is 'BTC_demo_key', so typing the following line would produce the same results:
    
    $ pw.getBalance()



    
    



