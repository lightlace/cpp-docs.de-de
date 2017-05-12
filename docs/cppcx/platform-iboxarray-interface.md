---
title: "Platform::IBoxArray-Schnittstelle | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBoxArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IBoxArray"
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBoxArray-Schnittstelle
,`IBoxArray` ist der Wrapper für Arrays von Werttypen, die über die Anwendungsbinärdateischnittstelle \(ABI\) übergeben werden oder in Auflistungen von `Platform::Object^`\-Elementen, wie die in XAML\-Steuerelementen, gespeichert werden.  
  
## Syntax  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### Parameter  
 `T`  
 Der Typ des geschachtelten Werts in jedem Arrayelement.  
  
## Hinweise  
 `IBoxArray` ist der [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)]\-Name \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) von `Windows::Foundation::IReferenceArray`.  
  
## Mitglieder  
 Die `IBoxArray`\-Schnittstelle erbt von der `IValueType`\-Schnittstelle.`IBoxArray` umfasst auch folgende Member:  
  
|Methode|Beschreibung|  
|-------------|------------------|  
|Wert|Gibt das nicht geschachtelte Array zurück, das zuvor in dieser `IBoxArray`\-Instanz gespeichert wurde.|  
  
## Siehe auch  
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)