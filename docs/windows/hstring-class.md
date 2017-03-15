---
title: "HString-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString"
dev_langs: 
  - "C++"
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HString-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bietet Unterstützung für die Bearbeitung von HSTRING\-Handles.  
  
## Syntax  
  
```cpp  
class HString;  
```  
  
## Hinweise  
 Die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ermöglicht den Zugriff auf die Zeichenfolgen durch HSTRING\-Handles.  Die HString\-Klasse stellt Hilfsfunktionen und Operatoren bereit, mit denen die Verwendung von HSTRING\-Handles vereinfacht wird.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HString::HString\-Konstruktor](../windows/hstring-hstring-constructor.md)|Initialisiert eine neue Instanz der HString\-Klasse.|  
|[HString::~HString\-Destruktor](../windows/hstring-tilde-hstring-destructor.md)|Zerstört die aktuelle Instanz der HString\-Klasse.|  
  
### Member  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HString::Set\-Methode](../windows/hstring-set-method.md)|Legt den Wert des aktuellen HString\-Objekts auf die angegebene Zeichenfolge mit Breitzeichen oder den angegebenen HString\-Parameter fest.|  
|[HString::Attach\-Methode](../windows/hstring-attach-method.md)|Ordnet das angegebene HString\-Objekt dem aktuellen HString\-Objekt zu.|  
|[HString::CopyTo\-Methode](../windows/hstring-copyto-method.md)|Kopiert das aktuelle HString\-Objekt zu einem HSTRING\-Objekt.|  
|[HString::Detach\-Methode](../windows/hstring-detach-method.md)|Hebt die Zuordnung des angegebenen HString\-Objekts zu seinem zugrunde liegenden Wert auf.|  
|[HString::GetAddressOf\-Methode](../windows/hstring-getaddressof-method.md)|Ruft einen Zeiger auf das zugrunde liegende HSTRING\-Handle ab.|  
|[HString::Get\-Methode](../windows/hstring-get-method.md)|Ruft den Wert des zugrunde liegenden HSTRING\-Handles ab.|  
|[HString::Release\-Methode](../windows/hstring-release-method.md)|Löscht den zugrunde liegenden Zeichenfolgenwert und initialisiert das aktuelle HString\-Objekt auf einen leeren Wert.|  
|[HString::MakeReference\-Methode](../windows/hstring-makereference-method.md)|Erstellt ein HStringReference\-Objekt aus einem angegebenen Zeichenfolgenparameter.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HString::Operator\=\-Operator](../windows/hstring-operator-assign-operator.md)|Verschiebt den Wert eines anderen HString\-Objekts zum aktuellen HString\-Objekt.|  
|[HString::Operator\=\=\-Operator](../windows/hstring-operator-equality-operator.md)|Gibt an, ob die zwei Parameter gleich sind.|  
|[HString::Operator\!\=\-Operator](../windows/hstring-operator-inequality-operator.md)|Gibt an, ob die zwei Parameter ungleich sind.|  
  
## Vererbungshierarchie  
 `HString`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)