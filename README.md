**侵权请联系:** youlianboshi@gmail.com
蓝灯破解版解压密码:youlianboshi

**油脸博士的订阅频道**
https://t.me/MTPdaili

__破解PC蓝灯核心代码__

```
HOOKDEF(ULONG, WINAPI, GetAdaptersAddresses, 
    __in ULONG Family,
    __in ULONG Flags,
    __reserved PVOID Reserved,
    __out_bcount_opt(*SizePointer) PIP_ADAPTER_ADDRESSES AdapterAddresses, 
    __inout PULONG SizePointer
    )
{
    srand( (unsigned)time( NULL ) );
 
    ULONG ret = Real_GetAdaptersAddresses(Family, Flags, Reserved, AdapterAddresses, SizePointer);
    while(AdapterAddresses){
        if (AdapterAddresses->PhysicalAddressLength >=5 ){
            AdapterAddresses->PhysicalAddress[0] += rand();
            AdapterAddresses->PhysicalAddress[1] += rand();
            AdapterAddresses->PhysicalAddress[2] += rand();
            AdapterAddresses->PhysicalAddress[3] += rand();
            AdapterAddresses->PhysicalAddress[4] += rand();
        }
 
        AdapterAddresses = AdapterAddresses->Next;
    }
    return ret;
}
```
