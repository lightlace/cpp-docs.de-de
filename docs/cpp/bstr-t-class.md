---
title: "_bstr_t-Klasse"
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
  - "_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t-Klasse"
  - "BSTR-Objekt"
  - "BSTR-Objekt, COM-Kapselung"
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Durch ein `_bstr_t`\-Objekt wird der [BSTR](assetId:///1b2d7d2c-47af-4389-a6b6-b01b7e915228)\-Datentyp gekapselt.  Die Klasse verwaltet die Zuordnung und Neuzuordnung von Ressourcen durch Funktionsaufrufe an **SysAllocString** und **SysFreeString** und andere `BSTR`\-APIs, falls erforderlich.  Die `_bstr_t`\-Klasse verwendet die Verweiszählung, um übermäßigen Mehraufwand zu vermeiden.  
  
### Konstruktion  
  
|||  
|-|-|  
|[\_bstr\_t](../cpp/bstr-t-bstr-t.md)|Erstellt ein `_bstr_t`\-Objekt.|  
  
### Vorgänge  
  
|||  
|-|-|  
|[Assign](../cpp/bstr-t-assign.md)|Kopiert ein `BSTR` in das `BSTR`, das von einem `_bstr_t` umschlossen wird.|  
|[Anfügen](../cpp/bstr-t-attach.md)|Verknüpft einen `_bstr_t`\-Wrapper mit einem `BSTR`.|  
|[copy](../cpp/bstr-t-copy.md)|Erstellt eine Kopie des gekapselten `BSTR`.|  
|[Trennen](../cpp/bstr-t-detach.md)|Gibt `BSTR` zurück, das von `_bstr_t` umschlossen ist, und trennt `BSTR` von `_bstr_t`.|  
|[GetAddress](../cpp/bstr-t-getaddress.md)|Zeigt auf den `BSTR`, der von einem `_bstr_t` umschlossen ist.|  
|[GetBSTR](../cpp/bstr-t-getbstr.md)|Zeigt auf den Anfang des `BSTR`, das vom `_bstr_t` umschlossen ist.|  
|[length](../cpp/bstr-t-length.md)|Gibt die Anzahl von Zeichen in `_bstr_t` zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../cpp/bstr-t-operator-equal.md)|Weist einem vorhandenen `_bstr_t`\-Objekt einen neuen Wert zu.|  
|[operator \+\=](../cpp/bstr-t-operator-add-equal-plus.md)|Fügt Zeichen an das Ende des `_bstr_t`\-Objekts an.|  
|[operator \+](../cpp/bstr-t-operator-add-equal-plus.md)|Verkettet zwei Zeichenfolgen.|  
|[operator \!](../cpp/bstr-t-operator-logical-not.md)|Überprüft, ob das gekapselte `BSTR` eine **NULL**\-Zeichenfolge ist.|  
|[operator \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/bstr-t-relational-operators.md)|Vergleicht zwei `_bstr_t`\-Objekte.|  
|[operator wchar\_t\* &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Extrahiert die Zeiger auf das gekapselten Unicode\- oder Mehrbyte\-`BSTR`\-Objekt.|  
  
## END Microsoft\-spezifisch  
  
## Anforderungen  
 **Header:** comutil.h  
  
 **Lib:** comsuppw.lib oder comsuppwd.lib \(Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).\)  
  
## Siehe auch  
 [Compilerklassen für COM\-Unterstützung](../cpp/compiler-com-support-classes.md)