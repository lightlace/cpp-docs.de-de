---
title: "Platform::Array-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Array-Klasse"
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Array-Klasse
Stellt ein änderbares, eindimensionales Array dar, das über die Anwendungsbinärdateischnittstelle \(ABI\) empfangen und übergeben werden kann.  
  
## Syntax  
  
```cpp  
  
template <typename T>  
    private ref class Array<TArg,1> :   
         public WriteOnlyArray<TArg, 1>,  
         public IBoxArray<TArg>  
  
```  
  
## Mitglieder  
 Platform::Array erbt alle Methoden aus [Platform::WriteOnlyArray\-Klasse](../cppcx/platform-writeonlyarray-class.md) und implementiert die `Value`\-Eigenschaft der [Platform::IBoxArray\-Schnittstelle](../cppcx/platform-iboxarray-interface.md).  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[Array\-Konstruktoren](../cppcx/array-constructors.md)|Initialisiert ein eindimensionales, änderbares Array von Typen, die vom Klassenvorlagenparameter *T* angegeben werden.|  
  
### Methoden  
 Siehe [Platform::WriteOnlyArray\-Klasse](../cppcx/platform-writeonlyarray-class.md).  
  
### Eigenschaften  
  
|||  
|-|-|  
|[Array::Value\-Eigenschaft](../cppcx/array-value-property.md)|Ruft ein Handle für das aktuelle Array ab.|  
  
## Hinweise  
 Die Array\-Klasse wird versiegelt und kann nicht vererbt werden.  
  
 Das Windows Runtime\-Typsystem unterstützt nicht das Konzept von verzweigten Arrays. Deshalb können Sie ein IVector\<Platform::Array\<T\>\> nicht als Rückgabewert oder Methodenparameter übergeben. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.  
  
 Weitere Informationen zur Verwendung von Platform::Array finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
 Das Windows Runtime\-Typsystem unterstützt nicht das Konzept von verzweigten Arrays. Deshalb können Sie ein IVector\<Platform::Array\<T\>\> nicht als Rückgabewert oder Methodenparameter übergeben. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.  
  
 Diese Klasse wird im Header "vccorlib.h" definiert, der automatisch vom Compiler eingeschlossen wird. Sie ist in IntelliSense, aber nicht im Objektkatalog, sichtbar, da sie kein öffentlicher, in platform.winmd definierter Typ ist.  
  
## Anforderungen  
 Compileroption: **\/ZW**  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)   
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)