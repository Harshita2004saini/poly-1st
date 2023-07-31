## Project setup
Hardhat
### Executing program
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
import "erc721a/contracts/ERC721A.sol";

contract MetaToken is ERC721A, Ownable {

       constructor() ERC721A("Harshita", "Haav") {}
           string private _baseTokenURI;
           uint start=0;
           uint next;

    function mint(address to,uint256 quantity) external payable {
        _mint(to, quantity);

    }
        function _baseURI() internal view override returns (string memory) {
        return _baseTokenURI;
    }
        function setBaseURI(string calldata baseURI) external onlyOwner {
        _baseTokenURI = baseURI;
    }
        function _startTokenId() internal view override returns(uint){
        return start;
    }
        function _nextTokenId() internal view override returns(uint){
        return(next);

    }
        function _nextTokenId(uint st) internal returns(uint){
        next=start+1;
        return next;
    }
function promptDescription() public pure returns(string memory,string[5] memory)
    {

              return ("The Prompts used to generate the images used on Adobe Firefly are:: ",["1.teddy","2. Car","3. eagle","4. golden retriever","5. monkey"]);
}

}
       
## Author
Harshita saini
21bcs5576@cuchd.in
