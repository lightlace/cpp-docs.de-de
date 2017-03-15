---
title: "rdx | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.rdx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdx attribute"
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# rdx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt einen Registrierungsschlüssel oder ändert einen vorhandenen Registrierungsschlüssel.  
  
## Syntax  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### Parameter  
 `key`  
 Der Name der erstellt werden soll oder geöffnet wurde Schlüssel.  
  
 `valuename`\(optional\)  
 Gibt das Feld auf Wert festgelegt werden soll.  Wenn ein Wert\-Feld mit diesem Namen bereits in der Schlüssel nicht vorhanden ist, wird er hinzugefügt.  
  
 *regtype*  
 Der Typ des Registrierungsschlüssels, der hinzugefügt wird.  Kann einen der folgenden Schritte aus: **Text**, **steht " dword**, **Binär**oder `CString`.  
  
## Hinweise  
 Das Attribut **rdx** C\+\+ erstellt oder ändert einen vorhandenen Registrierungsschlüssel für eine COM\-Komponente.  Das Attribut wird ein BEGIN\_RDX\_MAP\-Makro dem Objekt hinzu, das den Ziel Member implementiert.  `RegistryDataExchange`, eine Funktion, die aufgrund des BEGIN\_RDX\_MAP\-Makros eingefügt wird, kann zur Übertragung von Daten zwischen den Datenmember und der Registrierung verwendet werden  
  
 Dieses Attribut kann in Verbindung mit [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribute oder andere Attribute verwendet werden, das ein solcher Test vorhanden ist.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse** oder `struct`\-Member|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Beispiel  
 Der folgende Code fügt einen Registrierungsschlüssel hinzu, der MyValue dem System aufgerufen wird, das die CMyClass\-COM\-Komponente beschreibt.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [registration\_script](../windows/registration-script.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)