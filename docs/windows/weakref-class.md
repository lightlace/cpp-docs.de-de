---
title: WeakRef-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef
dev_langs: C++
helpviewer_keywords: WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8263595bdd564c313a8783a3a9baf0c6d562494
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="weakref-class"></a>WeakRef-Klasse
Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein WeakRef-Objekt verwaltet einen *starken Verweis*, der einem Objekt zugeordnet ist und gültig oder ungültig sein kann. Rufen Sie die Methode „As()“ oder „AsIID()“ auf, um einen starken Verweis abzurufen. Wenn der starke Verweis gültig ist, kann er auf das zugeordnete Objekt zugreifen. Wenn der starke Verweis ungültig ist (`nullptr`), ist der Zugriff auf das zugeordnete Objekt nicht möglich.  
  
 Ein WeakRef-Objekt wird normalerweise verwendet, um ein Objekt darzustellen, dessen Vorhandensein durch einen externen Thread oder eine externe Anwendung gesteuert wird. Erzeugen Sie beispielsweise ein WeakRef-Objekt aus einem Verweis auf ein Dateiobjekt. Solange die Datei geöffnet ist, ist der starke Verweis gültig. Wenn die Datei aber geschlossen wird, wird der starke Verweis ungültig.  
  
 Beachten Sie, dass es eine Verhaltensänderung bei den Methoden [As](../windows/weakref-as-method.md), [AsIID](../windows/weakref-asiid-method.md) und [CopyTo](../windows/weakref-copyto-method.md) im Windows 10 SDK gibt. Bisher konnten Sie nach dem Aufrufen einer dieser Methoden die WeakRef auf `nullptr` überprüfen, um zu bestimmen, ob ein starker Verweis erfolgreich abgerufen wurde, wie etwa im folgenden Code:  
  
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
  
 Dieser Code funktioniert bei Verwendung des Windows 10 SDKs (oder höher) nicht. Überprüfen Sie stattdessen den Zeiger, der übergeben wurde für `nullptr`.  
  
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
|[WeakRef::WeakRef-Konstruktor](../windows/weakref-weakref-constructor.md)|Initialisiert eine neue Instanz der WeakRef-Klasse.|  
|[WeakRef::~WeakRef-Destruktor](../windows/weakref-tilde-weakref-destructor.md)|Hebt die Initialisierung einer neuen Instanz der WeakRef-Klasse auf.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakRef::As-Methode](../windows/weakref-as-method.md)|Legt den angegebenen ComPtr-Zeigerparameter so fest, dass er die angegebene Schnittstelle darstellt.|  
|[WeakRef::AsIID-Methode](../windows/weakref-asiid-method.md)|Legt den angegebenen ComPtr-Zeigerparameter so fest, dass er die angegebene Schnittstellen-ID darstellt.|  
|[WeakRef::CopyTo-Methode](../windows/weakref-copyto-method.md)|Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[WeakRef::operator&-Operator](../windows/weakref-operator-ampersand-operator.md)|Gibt ein ComPtrRef-Objekt zurück, das das aktuelle WeakRef-Objekt darstellt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)