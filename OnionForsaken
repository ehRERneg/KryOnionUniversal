local _O_=string.char
local _X_={95,108,111,97,100,115,116,114,105,110,103}
local _F_=""
for i=1,#_X_ do _F_=_F_.._O_(_X_[i]) end

local encoded=[[
bG9jYWwgUmF5ZmllbGQgPSBsb2Fkc3RyaW5nKGdhbWU6SHR0cEdldCgiaHR0cHM6Ly9zaXJpdXMubWVudS9yYXlmaWVsZCIpKCkKCmxvY2FsIFdpbmRvdyA9IFJheWZpZWxkOkNy
ZWF0ZVdpbmRvdyh7CiAgICBOYW1lID0gIktyeU9uaW9uIHwgRk9SU0FLRU4iLAogICAgTG9hZGluZ1RpdGxlID0gIldlbGNvbWUgdG8gS3J5T25pb24iLAogICAgTG9hZGluZ1N1
YnRpdGxlID0gImJ5IGVocmVyLnZlciIsCiAgICBDb25maWd1cmF0aW9uU2F2aW5nID0gewogICAgICAgIEVuYWJsZWQgPSB0cnVlLAogICAgICAgIEZvbGRlck5hbWUgPSAiT25p
b25Jc0ZvcnNha2VuIiwKICAgICAgICBGaWxlTmFtZSA9ICJPbmlvbktyeUZvcnNha2VuIgogICAgfSwKICAgIEtleVN5c3RlbSA9IHRydWUsCiAgICBLZXlTZXR0aW5ncyA9IHsK
ICAgICAgICBUaXRsZSA9ICJLcnlPbmlvbiIsCiAgICAgICAgU3VidGl0bGUgPSAiS3J5T25pb24ga2V5IiwKICAgICAgICBOb3RlID0gInRyeSBPbmlvbiIsCiAgICAgICAgU2F2
ZUtleSA9IHRydWUsCiAgICAgICAgR3JhYktleUZyb21TaXRlID0gZmFsc2UsCiAgICAgICAgS2V5ID0geyJPbmlvbiIsICJPTklPTiIsICJlaGhoIiwgIk9OSU9OSVNHb09EIn0K
ICAgIH0KfSkKCi0tIFRhYnMgLS0KbG9jYWwgVGhpbmdzVGFiID0gV2luZG93OkNyZWF0ZVRhYigiVGhpbmdzIiwgMTMwNjI5MDQxODEpCmxvY2FsIEtyeXRoZXJUYWIgPSBXaW5k
b3c6Q3JlYXRlVGFiKCJLcnl0aGVyIiwgMTMwNjI5MDQxODEpCmxvY2FsIFN0YW1pbmFUYWIgPSBXaW5kb3c6Q3JlYXRlVGFiKCJTdGFtaW5hIiwgMTMwNjI5MDQxODEpCmxvY2Fs
IFBsYXllclRhYiA9IFdpbmRvdzpDcmVhdGVUYWIoIlBsYXllciIsIDEzMDYyOTA0MTgxKQoKLS0gQ29kaGVyZXMgY29udGludWEgY29tbyBub3JtYWwgc2NyaXB0IC0tCg==]]

local function _B64D(data)
    local b='ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'
    data=string.gsub(data,'[^'..b..'=]','')
    return (data:gsub('.',function(x)
        if (x == '=') then return '' end
        local r,f='',(string.find(b,x)-1)
        for i=6,1,-1 do r=r..(f%2^i - f%2^(i-1) > 0 and '1' or '0') end
        return r;
    end):gsub('%d%d%d?%d?%d?%d?%d?%d?',function(x)
        if (#x ~= 8) then return '' end
        local c=0
        for i=1,8 do c=c + (x:sub(i,i)=='1' and 2^(8-i) or 0) end
        return string.char(c)
    end))
end

local success,err=pcall(function()
    loadstring(_B64D(encoded))()
end)

if not success then warn("Onion Critical Error: ",err) end
