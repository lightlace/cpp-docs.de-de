---
title: "Platform::WriteOnlyArray-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
s.suite: 
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WriteOnlyArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::WriteOnlyArray-Klasse"
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 11
---
# Platform::WriteOnlyArray-Klasse
Stellt ein eindimensionales Array dar, das als Eingabeparameter verwendet wird, wenn der Aufrufer ein Array für die zu füllende Methode übergibt.  
  
 Diese Verweisklasse wird als privat in vccorlib.h deklariert. Daher wird sie nicht in Metadaten ausgegeben und kann nur von C\+\+ verwendet werden. Diese Klasse ist nur zur Verwendung als Eingabeparameter vorgesehen, der ein Array empfängt, das der Aufrufer zugeordnet hat. Sie ist nicht vom Benutzercode konstruierbar. Sie ermöglicht es einer C\+\+\-Methode, direkt in dieses Array zu schreiben – ein Muster, das als *FillArray*\-Muster bezeichnet wird. Weitere Informationen finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Syntax  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
 Diese Methoden verfügen über interne Zugreifbarkeit, das heißt, sie sind nur innerhalb der C\+\+\-App oder \-Komponente zugänglich.  
  
|Name|Beschreibung|  
|----------|------------------|  
|[WriteOnlyArray::begin\-Methode](../cppcx/writeonlyarray-begin-method.md)|Ein Iterator, der auf das erste Element des Arrays zeigt.|  
|[WriteOnlyArray::Data\-Eigenschaft](../cppcx/writeonlyarray-data-property.md)|Ein Zeiger auf den Datenpuffer.|  
|[WriteOnlyArray::end\-Methode](../cppcx/writeonlyarray-end-method.md)|Ein Iterator, der auf einen Punkt hinter dem letzten Element im Array zeigt.|  
|[WriteOnlyArray::FastPass\-Eigenschaft](../cppcx/writeonlyarray-fastpass-property.md)|Gibt an, ob das Array den FastPass\-Mechanismus verwenden kann. Dieser stellt eine Optimierung dar, die transparent vom System ausgeführt wird. Verwenden Sie dies nicht in Ihrem Code|  
|[WriteOnlyArray::Length\-Eigenschaft](../cppcx/writeonlyarray-length-property.md)|Gibt die Anzahl der Elemente des Arrays zurück.|  
|[WriteOnlyArray::set\-Funktion](../cppcx/writeonlyarray-set-function.md)|Legt das angegebene Element auf den angegebenen Wert fest.|  
  
## Vererbungshierarchie  
 `WriteOnlyArray`  
  
## Anforderungen  
 Compileroption: **\/ZW**  
  
 **Metadaten:** platform.winmd  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Erstellen von Windows\-Runtime\-Komponenten in C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)