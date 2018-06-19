---
title: RuntimeClass-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26c3542f5bea21d1b705cd3253e6828ff73677df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889006"
---
# <a name="runtimeclass-class"></a>RuntimeClass-Klasse
Stellt eine WinRT- oder COM-Klasse, die die angegebenen Schnittstellen erbt und die angegebene Windows-Runtime, Klassisches COM und schwachen Verweis Unterstützung bietet.  
  
Diese Klasse stellt die Implementierung Textbaustein WinRT und COM-Klassen, die die Implementierung von `QueryInterface`, `AddRef`, `Release` usw. verwaltet den Verweiszähler des Moduls und bietet Unterstützung für das Klassenfactory für Bereitstellung aktivierbare Objekte.
  
## <a name="syntax"></a>Syntax  
  
```
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```
  
#### <a name="parameters"></a>Parameter  
 `classFlags`  
Optionale Parameter. Eine Kombination aus einem oder mehreren [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumerationswerte. Die `__WRL_CONFIGURATION_LEGACY__` Makro kann definiert werden, um den Standardwert des ClassFlags für alle Common Language Runtime-Klassen im Projekt ändern. Wenn definiert, sind RuntimeClass-Instanzen in der Standardeinstellung nicht agile. Wenn Sie nicht definiert ist, sind RuntimeClass-Instanzen standardmäßig agile. Zur Vermeidung Mehrdeutigkeit immer angeben der Microsoft::WRL::FtmBase in `TInterfaces` oder RuntimeClassType::InhibitFtmBase. Beachten Sie: Wenn InhibitFtmBase und FtmBase sind, dass sowohl das Objekt verwendet wird nicht agil sein.
 
 `TInterfaces`  
Die Liste der Schnittstellen das Objekt implementiert, hinter IUnknown, "iinspectable" oder anderen Schnittstellen von gesteuert [RuntimeClassType](../windows/runtimeclasstype-enumeration.md). Es listet möglicherweise auch andere Klassen aus, insbesondere Microsoft::WRL::FtmBase abgeleitet werden, um das agil machen, das Objekt und dazu führen, dass IMarshal implementieren.
  
## <a name="members"></a>Member  
`RuntimeClassInitialize` Eine Funktion, die das Objekt initialisiert werden, wenn die MakeAndInitialize-Vorlagenfunktion verwendet wird, um das Objekt zu erstellen. Es gibt S_OK, wenn das Objekt erfolgreich initialisiert wurde oder eine COM-Fehlercode zurück, wenn Fehler bei der Initialisierung. Die COM-Fehlercode wird als der Rückgabewert der MakeAndInitialize weitergegeben. Beachten Sie, dass die RuntimeClassInitialize-Methode nicht aufgerufen wird, wenn die Vorlagenfunktion Stellen verwendet wird, um das Objekt zu erstellen.

### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[RuntimeClass::RuntimeClass-Konstruktor](../windows/runtimeclass-runtimeclass-constructor.md)|Initialisiert die aktuelle Instanz der RuntimeClass-Klasse.|  
|[RuntimeClass::~RuntimeClass-Destruktor](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der RuntimeClass-Klasse auf.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
Dies ist ein Implementierungsdetail.
  
## <a name="requirements"></a>Anforderungen  
**Header:** implements.h  
  
**Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)
