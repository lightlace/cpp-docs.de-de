---
title: "emitidl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.emitidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "emitidl attribute"
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# emitidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob alle nachfolgenden IDL\-Attribute in der generierten IDL\-Datei verarbeitet und gespeichert werden.  
  
## Syntax  
  
```  
  
      [ emitidl([boolean],  
   defaultimports=[boolean]  
) ] ;  
```  
  
#### Parameter  
 `boolean`  
 Mögliche Werte: **true**, **false**, **erzwungen**, **restricted**, **drücken Sie**oder **pop**.  
  
-   Wenn **true**IDL\-Kategorien alle Attribute, die in einer Quellcodedatei gefunden werden, in der generierten IDL\-Datei abgelegt wird.  Dies ist die Standardeinstellung für **emitidl**.  
  
-   Wenn **false**, IDL\-Kategorien keine Attribute, die in einer Quellcodedatei gefunden wurden, nicht in die generierten IDL\-Datei abgelegt wird.  
  
-   Wenn **restricted**IDL\-Attributen, können in der Datei ohne ein [Modul](../windows/module-cpp.md)\-Attribut aufweisen.  Der Compiler generiert keine IDL\-Datei.  
  
-   Wenn **erzwungen**, überschreibt ein nachfolgendes **restricted** Attribut, das eine Datei muss ein Modulattribut, wenn IDL\-Attribute in der Datei vorhanden ist.  
  
-   **drücken Sie** können Sie die aktuellen Einstellungen **emitidl** zu einem internen **emitidl** Stapel zu speichern, und legen Sie können **pop** , was zu **emitidl** Wert an oberster Position des Stapels ist **emitidl** internen.  
  
 **defaultimports** `boolean` *\=*\[\] \(optional\)  
 -   Wenn `boolean`**true**ist, wird docobj.idl in der generierten IDL\-Datei importiert.  Auch wenn eine IDL\-Datei mit demselben Namen H\-Datei als `#include` , dass Sie den Quellcode im selben Verzeichnis wie die H\-Datei gefunden wird, enthält die generierte IDL\-Datei eine Imports\-Anweisung für diese IDL\-Datei.  
  
-   Wenn `boolean`**false**ist, wird docobj.idl nicht in die generierten IDL\-Datei importiert.  Sie müssen mit [Import](../windows/import.md)IDL\-Dateien explizit importieren.  
  
## Hinweise  
 Nachdem das Attribut **emitidl** C\+\+ in einer Quellcodedatei gefunden wird, werden IDL\-Kategorien von Attributen in die generierten IDL\-Datei abgelegt.  Wenn kein Attribut vorhanden ist, werden **emitidl** IDL\-Attribute in der Quellcodedatei zur generierten IDL\-Datei ausgegeben.  
  
 Es ist möglich, mehrere **emitidl**\-Attribute in einer Quellcodedatei.  Wenn `[emitidl(false)];` in einer Datei ohne nachfolgendes `[emitidl(true)];`aufgetreten ist, werden keine Attribute in der generierten IDL\-Datei verarbeitet.  
  
 Jedes Mal, wenn der Compiler eine neue Datei gefunden wird, wird **emitidl** implizit in **true**festgelegt.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)