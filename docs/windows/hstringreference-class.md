---
title: "HStringReference-Klasse"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.  
  
## Syntax  
  
```cpp  
class HStringReference;  
```  
  
## Hinweise  
 Die Lebensdauer des Hintergrundpuffers im neuen HSTRING wird nicht von [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] verwaltet.  Der Aufrufer ordnet eine Quellzeichenfolge auf dem Stapelrahmen zu, um eine Heapzuweisung zu vermeiden und das Risiko eines Speicherverlusts auszuschließen.  Außerdem muss der Aufrufer sicherstellen, dass die Quellzeichenfolge während der Lebensdauer des angefügten HSTRING unverändert bleibt.  Weitere Informationen finden Sie unter [WindowsCreateStringReference function](assetId:///0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HStringReference::HStringReference\-Konstruktor](../windows/hstringreference-hstringreference-constructor.md)|Initialisiert eine neue Instanz der HStringReference\-Klasse.|  
  
### Member  
  
|Member|**Beschreibung**|  
|------------|----------------------|  
|[HStringReference::CopyTo\-Methode](../windows/hstringreference-copyto-method.md)|Kopiert das aktuelle HStringReference\-Objekt zu einem HSTRING\-Objekt.|  
|[HStringReference::Get\-Methode](../windows/hstringreference-get-method.md)|Ruft den Wert des zugrunde liegenden HSTRING\-Handles ab.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HStringReference::Operator\=\-Operator](../windows/hstringreference-operator-assign-operator.md)|Verschiebt den Wert eines anderen HStringReference\-Objekts zum aktuellen HStringReference\-Objekt.|  
|[HStringReference::Operator\=\=\-Operator](../windows/hstringreference-operator-equality-operator.md)|Gibt an, ob die zwei Parameter gleich sind.|  
|[HStringReference::Operator\!\=\-Operator](../windows/hstringreference-operator-inequality-operator.md)|Gibt an, ob die zwei Parameter ungleich sind.|  
  
## Vererbungshierarchie  
 `HStringReference`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)