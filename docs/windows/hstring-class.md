---
title: HString-Klasse | Microsoft Docs
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
ms.openlocfilehash: 8544a78fdbdab19f44081853f5f5878f980cec01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="hstring-class"></a>HString-Klasse
Eine Hilfsklasse für die Verwaltung der Lebensdauer des HSTRING mithilfe des RAII-Musters.
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>Hinweise  
 Windows-Runtime bietet Zugriff auf die Zeichenfolgen durch HSTRING-Handles. Die HString-Klasse stellt Hilfsfunktionen und Operatoren bereit, mit denen die Verwendung von HSTRING-Handles vereinfacht wird. Diese Klasse kann die Lebensdauer der HSTRING behandeln, die er über ein RAII-Muster besitzt. 
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HString::HString-Konstruktor](../windows/hstring-hstring-constructor.md)|Initialisiert eine neue Instanz der HString-Klasse.|  
|[HString::~HString-Destruktor](../windows/hstring-tilde-hstring-destructor.md)|Zerstört die aktuelle Instanz der HString-Klasse.|  
  
### <a name="members"></a>Member  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HString::Set-Methode](../windows/hstring-set-method.md)|Legt den Wert des aktuellen HString-Objekts auf die angegebene Zeichenfolge mit Breitzeichen oder den angegebenen HString-Parameter fest.|  
|[HString::Attach-Methode](../windows/hstring-attach-method.md)|Ordnet das angegebene HString-Objekt dem aktuellen HString-Objekt zu.|  
|[HString::CopyTo-Methode](../windows/hstring-copyto-method.md)|Kopiert das aktuelle HString-Objekt zu einem HSTRING-Objekt.|  
|[HString::Detach-Methode](../windows/hstring-detach-method.md)|Hebt die Zuordnung des angegebenen HString-Objekts zu seinem zugrunde liegenden Wert auf.|  
|[HString::GetAddressOf-Methode](../windows/hstring-getaddressof-method.md)|Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.|  
|[HString::Get-Methode](../windows/hstring-get-method.md)|Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.|  
|[HString::Release-Methode](../windows/hstring-release-method.md)|Löscht den zugrunde liegenden Zeichenfolgenwert und initialisiert das aktuelle HString-Objekt auf einen leeren Wert.|  
|[HString::MakeReference-Methode](../windows/hstring-makereference-method.md)|Erstellt ein HStringReference-Objekt aus einem angegebenen Zeichenfolgenparameter.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[HString::Operator=-Operator](../windows/hstring-operator-assign-operator.md)|Verschiebt den Wert eines anderen HString-Objekts zum aktuellen HString-Objekt.|  
|[HString::Operator==-Operator](../windows/hstring-operator-equality-operator.md)|Gibt an, ob die zwei Parameter gleich sind.|  
|[HString::Operator!=-Operator](../windows/hstring-operator-inequality-operator.md)|Gibt an, ob die zwei Parameter ungleich sind.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `HString`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)