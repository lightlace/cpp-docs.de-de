---
title: "event_source"
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
  - "vc-attr.event_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ereignisbehandlung, Attribute"
  - "Ereignisprotokolle, Ereignisquelle"
  - "Ereignisquellen, Erstellen"
  - "event_source-Attribut"
  - "Ereignisquellen"
  - "Ereignisbehandlung, Erstellen von Ereignisquellen"
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# event_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Ereignisquelle.  
  
## Syntax  
  
```  
  
       [ event_source(  
       type,  
optimize=[speed | size],  
decorate=[true | false]) ]  
```  
  
#### Parameter  
 `type`  
 Eine Enumeration von einem der folgenden Werte:  
  
-   `native` für nicht verwalteten C\/C\+\+\-Code \(Standard für nicht verwaltete Klassen\).  
  
-   `com` für COM\-Code. Sie müssen `coclass` verwenden, wenn `type`\=`com`. Dieser Wert erfordert, dass Sie folgende Headerdateien einschließen:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 Wenn `type`**native** ist, können Sie **optimize\=size** angeben, um anzugeben, dass mindestens 4 Bytes Speicherplatz für alle Ereignisse in einer Klasse vorhanden sind, oder **optimize\=speed** \(Standard\), um anzuzeigen, dass für jedes Event 4 Bytes Speicherplatz zur Verfügung stehen.  
  
 **decorate**  
 Wenn `type`**native** ist, können Sie **decorate\=false** angeben, um anzugeben, dass der erweiterte Name in der zusammengeführten Datei \(.mrg\) nicht den Namen der einschließenden Klasse enthalten soll. Mit [\/Fx](../build/reference/fx-merge-injected-code.md) können Sie MRG\-Dateien generieren.**decorate\=false**, ist die Standardeinstellung und führt zu vollqualifizierten Typnamen in der zusammengeführten Datei.  
  
## Hinweise  
 Das C\+\+\-Attribut **event\_source** gibt an, dass die Klasse oder Struktur, auf die es angewendet wird, eine Ereignisquelle sein wird.  
  
 **event\_source** wird in Verbindung mit dem Attribut [event\_receiver](../windows/event-receiver.md) und dem Schlüsselwort [\_\_event](../cpp/event.md) verwendet. Verwenden Sie **event\_receiver**, um Ereignisempfänger zu erstellen. Verwenden Sie `__event` für Methoden in der Ereignisquelle, um diese Methoden als Ereignisse anzugeben.  
  
> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.  
  
## Anforderungen  
  
### Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** wenn `type`\=**com**|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)