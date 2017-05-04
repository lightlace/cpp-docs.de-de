---
title: "Platform::Collections::InputIterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator-Klasse"
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::InputIterator-Klasse
Stellt einen InputIterator der Standardvorlagenbibliothek für Auflistungen bereit, die von der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] abgeleitet werden.  
  
## Syntax  
  
```  
template <  
   typename X  
>  
class InputIterator;  
```  
  
#### Parameter  
 `X`  
 Der Typname der InputIterator\-Vorlagenklasse.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|------------------|  
|`difference_type`|Ein Zeigerunterschied \(ptrdiff\_t\).|  
|`iterator_category`|Die Kategorie eines Eingabeiterators \(::std::input\_iterator\_tag\).|  
|`pointer`|Ein Zeiger auf eine `const` `X`.|  
|`reference`|Ein Verweis auf eine `const` `X`.|  
|`value_type`|Der `X`\-Typname.|  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[InputIterator::InputIterator\-Konstruktor](../cppcx/inputiterator-inputiterator-constructor.md)|Initialisiert eine neue Instanz der InputIterator\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[InputIterator::operator\!\=\-Operator](../cppcx/inputiterator-operator-inequality-operator.md)|Gibt an, ob der aktuelle InputIterator ungleich einem angegebenen InputIterator ist.|  
|[InputIterator::operator\*\-Operator](../cppcx/inputiterator-operator-decrementoperator.md)|Ruft einen Verweis auf das Element ab, das vom aktuellen InputIterator angegeben wird.|  
|[InputIterator::operator\+\+\-Operator](../cppcx/inputiterator-operator-increment-operator.md)|Inkrementiert den aktuellen InputIterator.|  
|[InputIterator::operator\=\=\-Operator](../cppcx/inputiterator-operator-equality-operator.md)|Gibt an, ob der aktuelle InputIterator gleich einem angegebenen InputIterator ist.|  
|[InputIterator::operator\-\>\-Operator](../cppcx/inputiterator-operator-arrow-operator.md)|Ruft die Adresse des Elements ab, auf das vom aktuellen InputIterator verwiesen wird.|  
  
## Vererbungshierarchie  
 `InputIterator`  
  
## Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  
  
## Siehe auch  
 [\(NOTINBUILD\) Plattformnamespace](http://msdn.microsoft.com/de-de/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)