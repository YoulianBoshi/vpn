**侵权请联系:** youlianboshi@gmail.com

签订了一年的卖身合同，离职后将去世界各地旅游✈，佛系更新😊有请大佬开发更好的工具😂😂

**油脸博士的订阅频道**
https://t.me/MTPdaili

__以下为破解PC蓝灯的核心代码__

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
