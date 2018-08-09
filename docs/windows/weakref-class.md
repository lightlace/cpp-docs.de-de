---
title: WeakRef-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88252e6bf4a5b7cad1ee6fcd0580d29f1bf5981a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641827"
---
# <a name="weakref-class"></a>WeakRef-Klasse
Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein **WeakRef** -Objekt verwaltet einen *starken Verweis*, der mit einem Objekt zugeordnet ist und gültig oder ungültig sein kann. Rufen Sie die `As()` oder `AsIID()` Methode, um einen starken Verweis abzurufen. Wenn der starke Verweis gültig ist, kann er auf das zugeordnete Objekt zugreifen. Wenn der starke Verweis ungültig ist (**"nullptr"**), das zugeordnete Objekt kann nicht zugegriffen werden.  
  
 Ein **WeakRef** Objekt wird normalerweise verwendet, um ein Objekt darstellt, dessen Vorhandensein durch einen externen Thread oder Anwendung gesteuert wird. Erstellen Sie z. B. eine **WeakRef** Objekt aus einem Verweis auf ein Dateiobjekt. Solange die Datei geöffnet ist, ist der starke Verweis gültig. Wenn die Datei aber geschlossen wird, wird der starke Verweis ungültig.  
  
 Beachten Sie, dass es eine Verhaltensänderung bei den Methoden [As](../windows/weakref-as-method.md), [AsIID](../windows/weakref-asiid-method.md) und [CopyTo](../windows/weakref-copyto-method.md) im Windows 10 SDK gibt. Zuvor, nach dem Aufrufen einer dieser Methoden, Überprüfen der WeakRef **"nullptr"** zu bestimmen, ob ein starker Verweis erfolgreich, wie im folgenden Code abgerufen wurde:  
  
```cpp  
WeakRef wr;  
strongComptrRef.AsWeak(&wr);  
  
// Now suppose that the object strongComPtrRef points to no longer exists  
// and the following code tries to get a strong ref from the weak ref:  
ComPtr<ISomeInterface> strongRef;  
HRESULT hr = wr.As(&strongRef);  
  
// This check won't work with the Windows 10 SDK version of the library.  
// Check the input pointer instead.  
if(wr == nullptr)  
{  
    wprintf(L"Couldn’t get strong ref!");  
}  
```  
  
 Dieser Code funktioniert bei Verwendung des Windows 10 SDKs (oder höher) nicht. Überprüfen Sie stattdessen den Zeiger, der übergeben wurde für **"nullptr"**.  
  
```cpp  
if (strongRef == nullptr)  
{  
    wprintf(L"Couldn't get strong ref!");  
}  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakRef::WeakRef-Konstruktor](../windows/weakref-weakref-constructor.md)|Initialisiert eine neue Instanz der dem **WeakRef** Klasse.|  
|[WeakRef::~WeakRef-Destruktor](../windows/weakref-tilde-weakref-destructor.md)|Hebt die Initialisierung der aktuellen Instanz von der **WeakRef** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakRef::As-Methode](../windows/weakref-as-method.md)|Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstelle darstellt.|  
|[WeakRef::AsIID-Methode](../windows/weakref-asiid-method.md)|Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstellen-ID darstellt.|  
|[WeakRef::CopyTo-Methode](../windows/weakref-copyto-method.md)|Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakRef::operator&-Operator](../windows/weakref-operator-ampersand-operator.md)|Gibt eine `ComPtrRef` -Objekt, das der aktuelle darstellt **WeakRef** Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)