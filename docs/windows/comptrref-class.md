---
title: "ComPtrRef-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRef-Klasse"
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ComPtrRef-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### Parameter  
 `T`  
 Ein [ComPtr \<T\>](../windows/comptr-class.md)\-Typ oder einen davon abgeleiteten Typ, nicht nur die Schnittstelle, die vom ComPtr dargestellt wird.  
  
## Hinweise  
 Stellt einen Verweis auf ein Objekt des Typs ComPtrT \<\>dar.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ComPtrRef::ComPtrRef\-Konstruktor](../windows/comptrref-comptrref-constructor.md)|Initialisiert eine neue Instanz der ComPtrRef\-Klasse vom angegebenen Zeiger auf einen anderen ComPtrRef\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ComPtrRef::GetAddressOf\-Methode](../windows/comptrref-getaddressof-method.md)|Ruft die Adresse eines Zeigers zur Schnittstelle ab, die durch das aktuelle ComPtrRef\-Objekt dargestellt wird.|  
|[ComPtrRef::ReleaseAndGetAddressOf\-Methode](../windows/comptrref-releaseandgetaddressof-method.md)|Löscht das aktuelle ComPtrRef\-Objekt und gibt ein Zeiger\-zu\-einZeiger zur Schnittstelle zurück, die vom ComPtrRef\-Objekt dargestellt wird.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ComPtrRef::operator InterfaceType\*\*\-Operator](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Löscht das aktuelle ComPtrRef\-Objekt und gibt ein Zeiger\-zu\-einZeiger zur Schnittstelle zurück, die vom ComPtrRef\-Objekt dargestellt wird.|  
|[ComPtrRef::operator T\*\-Operator](../windows/comptrref-operator-t-star-operator.md)|Gibt den Wert des [ptr\_](../windows/comptrrefbase-ptr-data-member.md) Datenmembers des aktuellen ComPtrRef\-Objekts zurück.|  
|[ComPtrRef::operator void\*\*\-Operator](../windows/comptrref-operator-void-star-star-operator.md)|Löscht das aktuelle ComPtrRef\-Objekt, wandelt den Zeiger auf die Schnittstelle, die vom ComPtrRef\-Objekt als WIQ\-Datei Zeiger\-zu\-Zeiger\-zu `void` dargestellt wird, und gibt dann den Umwandlungszeiger zurück.|  
|[ComPtrRef::operator\*\-Operator](../windows/comptrref-operator-star-operator.md)|Ruft den Mauszeiger zur Schnittstelle ab, die durch das aktuelle ComPtrRef\-Objekt dargestellt wird.|  
|[ComPtrRef::operator\=\=\-Operator](../windows/comptrref-operator-equality-operator.md)|Gibt an, ob zwei ComPtrRef\-Objekte gleich sind.|  
|[ComPtrRef::operator\!\=\-Operator](../windows/comptrref-operator-inequality-operator.md)|Gibt an, ob zwei ComPtrRef\-Objekte nicht gleich sind.|  
  
## Vererbungshierarchie  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)