---
title: "_U_STRINGorID Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL._U_STRINGorID"
  - "ATL::_U_STRINGorID"
  - "_U_STRINGorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_STRINGorID class"
  - "U_STRINGorID class"
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# _U_STRINGorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Argumentadapterklasse können entweder `LPCTSTR` Ressourcennamen \(s\) oder an eine Funktion übergeben werden **UINT** Ressourcen\-IDs \(s\), ohne den Aufrufer benötigen, die ID in eine Zeichenfolge mit dem **MAKEINTRESOURCE**\-Makros zu konvertieren.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class _U_STRINGorID  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[\_U\_STRINGorID::\_U\_STRINGorID](../Topic/_U_STRINGorID::_U_STRINGorID.md)|Der \-Konstruktor.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[\_U\_STRINGorID::m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md)|Der Ressourcenbezeichner.|  
  
## Hinweise  
 Diese Klasse ist für das Implementieren von Wrappern zur Windows\-Ressourcenverwaltung APIs wie die [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) und [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990)\-Funktionen entwickelt, die akzeptieren ein `LPCTSTR`, ist das Argument entweder der Name einer Ressource oder der ID möglicherweise  
  
 Die Klasse definiert zwei Konstruktorüberladungen: Sie akzeptiert ein `LPCTSTR`\-Argument und der andere akzeptiert ein **UINT**\-Argument.  Das **UINT**\-Argument wird einem Ressourcentyp konvertiert, der mit Windows\-RessourceVerwaltung Funktionen mithilfe des **MAKEINTRESOURCE**\-Makros und das Ergebnis gespeichert werden im Einzelnen Datenmember der Klasse, [m\_lpstr](../Topic/_U_STRINGorID::m_lpstr.md) kompatibel ist.  Das Argument in `LPCTSTR`\-Konstruktor wird direkt ohne Konvertierung gespeichert.  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)