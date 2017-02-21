---
title: "progid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "progid attribute"
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die ProgID für ein COM\-Objekt an.  
  
## Syntax  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### Parameter  
 *Name*  
 Die ProgID, das das Objekt darstellt.  
  
 ProgIDs\-Geschenk einer lesbaren Version der Klassenbezeichner \(CLSID\) verwendet, um COM\-\/ActiveX Objekte zu identifizieren.  
  
## Hinweise  
 Das Attribut **progid** C\+\+ können Sie die ProgID für ein COM\-Objekt angeben.  Ein ProgID hat das Formular *name1.name2.version*.  Wenn Sie keine *Version* für eine ProgID angeben, wird die standardmäßige Version 1.  Wenn Sie nicht angeben, *name1.name2*ist der Standardname *classname.classname**.* Wenn Sie nicht angeben **progid** und Sie **vi\_progid**angeben, werden *name1.name2*von **vi\_progid** entnommen und die Version \(der folgenden sequenziellen Zahl\) angefügt wird.  
  
 Wenn in einem Attributblock, der **progid** verwendet, nicht `uuid`verwendet, überprüft der Compiler die Registrierung, um festzustellen, ob `uuid` für die angegebene **progid**vorhanden ist.  Wenn **progid** nicht angegeben wird, werden die Version \(und der Co\-Klassen, wenn erstellt werden, eine Co\-Klasse\) verwendet, um **progid**zu generieren.  
  
 Das bedeutet**progid** coclass\-Attribut, d.h., wenn Sie **progid**angeben, wird die **coclass** , wie dasselbe Ziel und **progid**\-Attribute angibt.  
  
 Das **progid**\-Attribut wird eine Klasse mit dem angegebenen Namen automatisch registriert werden.  Die generierten IDL\-Datei wird nicht den **progid**\-Wert an.  
  
 Wenn dieses Attribut innerhalb eines Projekts verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs.  Neben den oben beschriebenen Verhalten sind die Informationen, die mit diesem Attribut angegeben werden, in der **GetProgID**\-Funktion eingefügt, durch das coclass\-Attribut.  Weitere Informationen finden Sie unter [Co\-Klasse](../windows/coclass.md)\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [Co\-Klasse](../windows/coclass.md) B. für eine Verwendung von **progid**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)