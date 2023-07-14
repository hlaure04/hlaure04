contact MyToken {

// public variables here
    string TokenName= "Enhypen";
    string TokenAbbrv= "ENHY";
    uint TotalSupply=0;
    
     // mapping variable here
    mapping(address=>uint); public bal;


    // mint function
    function mint (address _address, uint _value); public{
        TotalSupply += _value;
        bal[_address] += _value;

    }

    // burn function
    function burn(address _address, uint _value); public{
        if (bal[_address] >= _value) {
        TotalSupply -= _value;
        bal[_address] -= _value;
        }
    }
}
