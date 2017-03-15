---
title: "threading (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.threading"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threading attribute"
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# threading (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das Threadingmodell für ein COM\-Objekt an.  
  
## Syntax  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### Parameter  
 ***Modell*** \(optional\)  
 Eines der folgenden Threadingmodelle:  
  
-   **Apartment** \(Apartmentthreading\)  
  
-   **neutral** \(.NET Framework\-Komponenten ohne Benutzeroberfläche\)  
  
-   **Einfach** \(einfaches Threading\)  
  
-   **frei** \(Freethreading\)  
  
-   **beides** \(Apartment und Freethreading\)  
  
 Der Standardwert ist **Apartment**.  
  
## Hinweise  
 Das Attribut **Threading** C\+\+ nicht angezeigt, in der generierten IDL\-Datei wird jedoch in der Implementierung des COM\-Objekts verwendet werden.  
  
 In den ATL\-Projekten wenn das [Co\-Klasse](../windows/coclass.md)\-Attribut vorhanden ist, wird das Threadingmodell, das vom *Modell* angegeben wurde, als der Vorlagenparameter zur [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)\-Klasse übergeben, durch das coclass\-Attribut eingefügt.  
  
 Der Wächter den Zugriff auf [event\_source](../windows/event-source.md)auch **Threading**\-Attributs.  
  
## Beispiel  
 Weitere Informationen finden Sie im [lizenziert](../windows/licensed.md) Beispiel für eine Beispiel verwenden aus **Threading**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co\-Klasse**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Multithreadingunterstützung für älteren Code \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Neutral Apartments](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)