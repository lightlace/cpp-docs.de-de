---
title: 'Platform:: GUID-Wertklasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
dev_langs:
- C++
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d971d4cce8dc3a9d01a666bc8e0e6333f85260c8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751568"
---
# <a name="platformguid-value-class"></a>Platform::Guid-Wertklasse
Stellt eine [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) Geben Sie die Windows-Runtime-Typsystem.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public value struct Guid  
```  
  
### <a name="members"></a>Member  
 GUID enthält die Methoden Equals(), GetHashCode() und ToString(), die von der [Platform::Object Class](../cppcx/platform-object-class.md), und die GetTypeCode()-Methode, die von der [Platform::Type Class](../cppcx/platform-type-class.md). Der Guid verfügt auch über die folgenden Member.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[Guid](#ctor)|Initialisiert eine neue Instanz der Guid-Struktur.|  
|[operator==](#operator-equality)|Entspricht Operator.|  
|[Operator!=](#operator-not-equal)|Entspricht nicht Operator.|  
|[Operator()](#operator-call)|Konvertiert ein GUID in ein GUID.|  
  
### <a name="remarks"></a>Hinweise  
 Ein Beispiel für eine neue Platform:: GUID mithilfe der Windows-Funktion [CoCreateGuid](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateguid), finden Sie unter [WinRT-Komponente: wie generiert eine GUID?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client (Min.):** Windows 8  
  
 **Unterstützter Server (Min.):** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

 
## <a name="ctor"></a> GUID:: GUID-Konstruktoren
Initialisiert eine neue Instanz einer GUID-Struktur.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  );  
  
    Guid(GUID m);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n );  
```  
  
### <a name="parameters"></a>Parameter  
 `a`  
 Die ersten 4 Bytes der GUID.  
  
 `b`  
 Die nächsten 2 Bytes der GUID.  
  
 `c`  
 Die nächsten 2 Bytes der GUID.  
  
 `d`  
 Das nächste Byte der GUID.  
  
 `e`  
 Das nächste Byte der GUID.  
  
 `f`  
 Das nächste Byte der GUID.  
  
 `g`  
 Das nächste Byte der GUID.  
  
 `h`  
 Das nächste Byte der GUID.  
  
 `i`  
 Das nächste Byte der GUID.  
  
 `j`  
 Das nächste Byte der GUID.  
  
 `k`  
 Das nächste Byte der GUID.  
  
 `m`  
 Eine GUID wie in der Definition.  
  
 `n`  
 Die restlichen 8 Bytes der GUID.  
  

## <a name="operator-equality"></a> GUID::Operator ==-Operator
Vergleicht zwei Guids.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::Guid::operator==  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn zwei Guids identisch sind.

## <a name="operator-inequality"></a> GUID::Operator! =-Operator
Vergleicht zwei Guids.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::Guid::operator!=  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die zwei Guids nicht gleich sind.



## <a name="operator-call"></a> GUID::Operator()-Operator
Konvertiert implizit eine [GUID-Struktur](https://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)GUID in eine Platform:: GUID.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::Guid operator()  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine GUID-Struktur.  
  
  
## <a name="see-also"></a>Siehe auch  
 [Platform-namespace](../cppcx/platform-namespace-c-cx.md)