---
title: "event_receiver | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_receiver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event_receiver attribute"
  - "event receivers"
  - "events [C++], event receivers (sinks)"
  - "event handling [C++], attributes"
  - "event handling [C++], creating receiver"
  - "event sinks, creating"
  - "event sinks"
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# event_receiver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen Ereignisempfänger \(Senke\).  
  
## Syntax  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### Parameter  
 `type`  
 Eine Enumeration mit einem der folgenden Werte:  
  
-   `native` für nicht verwaltete C\/C\+\+\-Code \(Standard für systemeigene Klassen\).  
  
-   `com` für COM\-Code.  Dieser Wert setzt voraus, dass Sie die folgenden Headerdateien umfassen:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout\_dependent**  
 Geben Sie nur bei `type`\= *layout\_dependent***COM**an.  ist ein boolescher Wert*layout\_dependent* :  
  
-   **true** bedeutet, dass die Signatur des Empfängers der Delegat im Ereignisprotokoll die genau übereinstimmen müssen, auf die sie gehakte Quelle in den Ereignisdaten.  Das Ereignis empfänger\-Handler Namen müssen die Namen übereinstimmen, die in der relevanten Quellschnittstelle des Ereignisses angegeben werden.  Sie müssen **coclass** verwenden, wenn *layout\_dependent,* sind **true**.  Es ist etwas effizienter, **true**anzugeben.  
  
-   **false** \(Standard\) gibt an, dass die Aufrufkonvention und Speicherklasse \(virtual statisch und andere\) die Ereignismethode und die Handler nicht übereinstimmen müssen. Name der Handler dennoch ausführen, die Ereignisquellen schnittstellenmethoden Namen übereinstimmt.  
  
## Hinweise  
 Das Attribut **event\_receiver** C\+\+ gibt an, dass die Klasse oder die Struktur, auf die es angewendet wird, ein Ereignisempfänger sind, mithilfe des einheitlichen Ereignismodells von Visual C\+\+.  
  
 **event\_receiver** wird mit dem [event\_source](../windows/event-source.md)\-Attribut und der [\_\_hook](../cpp/hook.md) und [\_\_unhook](../cpp/unhook.md) Schlüsselwörtern verwendet.  Verwendung **event\_source** , Ereignisquellen zu erstellen.  Verwenden Sie `__hook` innerhalb der Methoden eines Ereignisempfängers, um \(„Ereignisempfänger“\) Hook Methoden Ereignisse einer Ereignisquelle zuzuordnen.  Verwendung `__unhook` , sie zu trennen.  
  
 *layout\_dependent* wird nur für COM\-Ereignisempfänger \(`type`\=**COM**\) angegeben.  Der Standardwert für *layout\_dependent* ist **false**.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** wenn layout\_dependent\=**true**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_source](../windows/event-source.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)