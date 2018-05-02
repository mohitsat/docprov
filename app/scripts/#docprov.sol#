‌pragma solidity ^0.4.2;
contract DocProv {
    event CreatedFile(string author);
    uint256 fileId = 0;
    uint256 ChangeId = 0;
    event UpdateFile(string author,string what, uint fileId);
    
    function getFileCount() returns (uint){
    return fileId;
    }
    
    function getChangeCount() returns (uint){
    return ChangeId;
    }
    
    mapping (uint256 => uint256[] )FileChange;
    struct change {
        string who;
        string date;
        string what;
    }
    
    mapping(uint256 => change)changeInfo;
    function DocProv() {
        createFile("Abhishek", "New File", "4-20-2018");
    }
    
    function getChangeList(uint256 fileId) returns(uint256[]) {
        uint256[] temp = FileChange[fileId];
        return temp;
    }
    
    function createFile(string who, string what, string when ) {
        fileId++;
        ChangeId++;
        FileChange[fileId].push(ChangeId) ;
        var changedata = changeInfo[ChangeId];
        changedata.who = who;
        changedata.date = when;
        changedata.what = what;
        CreatedFile(who);
    }
    function updateFile(uint256 fileId, string who, string what, string when) {
        ChangeId++;
        FileChange[fileId].push(ChangeId) ;
        var changedata = changeInfo[ChangeId];
        changedata.who = who;
        changedata.date = when;
        changedata.what = what;
        UpdateFile(who,what,fileId);
    }
    function getChangewho(uint256 changeid) returns(string ) {
        var changed = changeInfo[changeid];
        string rwho = changed.who;
        return rwho;
    }
    
    function getChangedata(uint256 changeid) returns(string ) {
        var changed = changeInfo[changeid];
        string rdate = changed.date;
        return rdate;
    }
    
    function getChangewhat(uint256 changeid) returns(string ) {
        var changed = changeInfo[changeid];
        string rwhat = changed.what;
        return rwhat;
    }
    
    
}

