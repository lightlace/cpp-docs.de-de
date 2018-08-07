---
title: HString-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 868d0a4e2d84add447c95bfcd9690c8a17850718
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571450"
---
# <a name="hstring-class"></a>HString-Klasse
Eine Hilfsklasse für die Verwaltung der Lebensdauer des ein HSTRING mit das RAII-Muster.
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Windows-Runtime ermöglicht den Zugriff auf die Zeichenfolgen durch HSTRING-Handles. Die **HString** Klasse enthält Hilfsfunktionen und Operatoren zur Vereinfachung der Verwendung von HSTRING-Handles. Diese Klasse kann die Lebensdauer der HSTRING verarbeiten, die sie über ein RAII-Muster besitzt. 
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HString::HString-Konstruktor](../windows/hstring-hstring-constructor.md)|Initialisiert eine neue Instanz der dem **HString** Klasse.|  
|[HString::~HString-Destruktor](../windows/hstring-tilde-hstring-destructor.md)|Zerstört die aktuelle Instanz von der **HString** Klasse.|  
  
### <a name="members"></a>Member  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HString::Set-Methode](../windows/hstring-set-method.md)|Legt den Wert des aktuellen **HString** Objekt, das die angegebene Zeichenfolge mit Breitzeichen oder **HString** Parameter.|  
|[HString::Attach-Methode](../windows/hstring-attach-method.md)|Ordnet die angegebene **HString** Objekt mit dem aktuellen **HString** Objekt.|  
|[HString::CopyTo-Methode](../windows/hstring-copyto-method.md)|Kopiert das aktuelle **HString** Objekt zu einem HSTRING-Objekt.|  
|[HString::Detach-Methode](../windows/hstring-detach-method.md)|Hebt die Zuordnung der angegebenen **HString** Objekt von seinem zugrunde liegenden Wert.|  
|[HString::GetAddressOf-Methode](../windows/hstring-getaddressof-method.md)|Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.|  
|[HString::Get-Methode](../windows/hstring-get-method.md)|Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.|  
|[HString::Release-Methode](../windows/hstring-release-method.md)|Löscht den zugrunde liegenden Zeichenfolgenwert und initialisiert die aktuelle **HString** Objekt auf einen leeren Wert.|  
|[HString::MakeReference-Methode](../windows/hstring-makereference-method.md)|Erstellt eine `HStringReference` Objekt aus einem angegebenen Zeichenfolgenparameter.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HString::Operator=-Operator](../windows/hstring-operator-assign-operator.md)|Verschiebt den Wert eines anderen **HString** -Objekt mit dem aktuellen **HString** Objekt.|  
|[HString::Operator==-Operator](../windows/hstring-operator-equality-operator.md)|Gibt an, ob die zwei Parameter gleich sind.|  
|[HString::Operator!=-Operator](../windows/hstring-operator-inequality-operator.md)|Gibt an, ob die zwei Parameter ungleich sind.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HString`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)