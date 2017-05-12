---
title: "Platform::Object-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Objektklasse"
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Object-Klasse
Stellt gemeinsames Verhalten für Verweisklassen und Referenzstrukturen in Windows Store\-Apps bereit. Alle Verweisklassen\- und Referenzstruktur\-Instanzen sind implizit konvertierbar in Platform::Object^ und können seine virtuelle ToString\-Methode überschreiben.  
  
## Syntax  
  
```scr  
public ref class Object : Object  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Object::Object\-Konstruktor](../cppcx/object-object-constructor.md)|Initialisiert eine neue Instanz der Objektklasse.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Object::Equals\-Methode](../cppcx/object-equals-method.md)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|  
|[Object::GetHashCode\-Methode](../cppcx/object-gethashcode-method.md)|Gibt den Hashcode für diese Instanz zurück.|  
|[Object::ReferenceEquals\-Methode](../cppcx/object-referenceequals-method.md)|Stellt fest, ob die angegebenen Objekt\-Instanzen dieselbe Instanz sind.|  
|[ToString\-Methode](../cppcx/object-tostring-method-c-cx.md)|Gibt eine Zeichenfolge zurück, die das aktuelle Objekt darstellt. Kann überschrieben werden.|  
|[GetType\-Methode](../cppcx/object-gettype-method.md)|Ruft einen [Platform::Type](../cppcx/platform-type-class.md) ab, der die aktuelle Instanz beschreibt.|  
  
## Vererbungshierarchie  
 `Object`  
  
 `Object`  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
 **Namespace:** Platform  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)