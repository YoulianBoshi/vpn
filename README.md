**侵权请联系:** youlianboshi@gmail.com

由于工作原因，后续更新，请大家谅解

**更多免费MTP、HTTPS、Ikev2代理节点订阅频道不怕迷路**
https://t.me/MTPdaili

**有人私信要源码，以下是核心代码**

```
破解原理为生成随机MAC地址欺骗程序达到无限试用
以下是核心代码部分(api hook)

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
