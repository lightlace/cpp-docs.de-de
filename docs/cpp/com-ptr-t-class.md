---
title: "_com_ptr_t-Klasse"
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
  - "_com_ptr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_ptr_t-Klasse"
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ein `_com_ptr_t`\-Objekt kapselt einen COM\-Schnittstellenzeiger und wird als "intelligenter" Zeiger bezeichnet.  Diese Vorlagenklasse verwaltet die Zuordnung und Aufhebung der Zuordnung von Ressourcen mit Aufrufen der **IUnknown**\-Memberfunktionen: `QueryInterface`, `AddRef` und **Release**.  
  
 Ein intelligenter Zeiger wird in der Regel durch die typedef\-Definition verwiesen, die vom **\_COM\_SMARTPTR\_TYPEDEF**\-Makro bereitgestellt wird.  Dieses Makro erwartet einen Schnittstellennamen und die IID und deklariert eine Spezialisierung von `_com_ptr_t` mit dem Namen der Schnittstelle sowie dem Suffix `Ptr`.  Beispiel:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 deklariert die `_com_ptr_t`\-Spezialisierung **IMyInterfacePtr**.  
  
 Ein Satz von [Funktionsvorlagen](../cpp/relational-function-templates.md), nicht Mitglieder dieser Vorlagenklasse, unterstützen Vergleiche mit einem intelligenten Zeiger auf der rechten Seite des Vergleichsoperators.  
  
### Konstruktion  
  
|||  
|-|-|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-com-ptr-t.md)|Erstellt ein `_com_ptr_t`\-Objekt.|  
  
### Vorgänge auf niedriger Stufe  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Ruft die `AddRef`\-Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.|  
|[Anfügen](../cpp/com-ptr-t-attach.md)|Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Erstellt eine neue Instanz eines Objekts, dem ein **CLSID** oder **ProgID** übergeben wurde.|  
|[Trennen](../cpp/com-ptr-t-detach.md)|Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Wird einer vorhandenen Instanz eines Objekts mit **CLSID** oder **ProgID** angefügt.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Gibt den gekapselten Schnittstellenzeiger zurück.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Ruft die `QueryInterface`\-Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.|  
|[Release](../cpp/com-ptr-t-release.md)|Ruft die **Release**\-Memberfunktion von **IUnknown** für den gekapselten Schnittstellenzeiger auf.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../cpp/com-ptr-t-operator-equal.md)|Weist einem vorhandenen `_com_ptr_t`\-Objekt einen neuen Wert zu.|  
|[Operatoren \=\=, \!\=, \<, \>, \<\=, \>\=](../cpp/com-ptr-t-relational-operators.md)|Vergleichen Sie das intelligente Zeigerobjekt mit einem anderen intelligenten Zeiger, unformatierten Schnittstellenzeiger oder **NULL**.|  
|[Extractors](../cpp/com-ptr-t-extractors.md)|Extrahieren Sie den gekapselten COM\-Schnittstellenzeiger.|  
  
## END Microsoft\-spezifisch  
  
## Anforderungen  
 **Header:** comip.h  
  
 **Lib:** comsuppw.lib oder comsuppwd.lib \(Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).\)  
  
## Siehe auch  
 [Compilerklassen für COM\-Unterstützung](../cpp/compiler-com-support-classes.md)