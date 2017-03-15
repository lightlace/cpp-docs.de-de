---
title: "vi_progid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.vi_progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vi_progid attribute"
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# vi_progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt ein versionsunabhängiges ProgID des Formulars an.  
  
## Syntax  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### Parameter  
 *Name*  
 Das versionsunabhängige Programm\-ID, das das Objekt darstellt.  
  
 ProgIDs\-Geschenk einer lesbaren Version der Klassenbezeichner \(CLSID\) verwendet, um COM\-\/ActiveX Objekte zu identifizieren.  
  
## Hinweise  
 Das Attribut **vi\_progid** C\+\+ können Sie ein versionsunabhängiges ProgID für ein COM\-Objekt angeben.  Ein ProgID hat das Formular *name1.name2.version*.  Ein versionsunabhängiges ProgID hat keine *Version*.  Es ist möglich, **progid** und die **vi\_progid**\-Attribute für eine Co\-Klasse anzugeben.  Wenn Sie nicht angeben, ist das **vi\_progid**versionsunabhängige Programm\-ID sich der Wert des vom [ProgID](../windows/progid.md)\-Attribut angegeben ist.  
  
 Das bedeutet**vi\_progid** coclass\-Attribut, d.h., wenn Sie **vi\_progid**angeben, wird die **coclass** , wie dasselbe Ziel und **vi\_progid**\-Attribute angibt.  
  
 Das **vi\_progid**\-Attribut wird eine Klasse mit dem angegebenen Namen automatisch registriert werden.  Die generierten IDL\-Datei wird nicht der ProgID\-Wert an.  
  
 In den ATL\-Projekten wenn das [Co\-Klasse](../windows/coclass.md)\-Attribut vorhanden ist, wird das angegebene ProgID \( **GetVersionIndependentProgID** durch die Funktion durch das Einfügen coclass\-Attribut\).  
  
## Beispiel  
 Weitere Informationen finden Sie im [Co\-Klasse](../windows/coclass.md) Beispiel für eine Beispiel verwenden aus **vi\_progid**.  
  
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
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)