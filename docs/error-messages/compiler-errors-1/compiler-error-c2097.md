---
title: "Compilerfehler C2097 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2097"
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2097
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unzulässige Initialisierung  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Initialisierung einer Variablen mit einem nicht konstanten Wert.  
  
2.  Die Initialisierung einer short\-Adresse mit einer long\-Adresse.  
  
3.  Bei Kompilierung mit **\/Za** die Initialisierung einer lokalen Struktur, Union oder eines Arrays mit einem nicht konstanten Ausdruck.  
  
4.  Die Initialisierung mit einem Ausdruck, der einen Operator Komma enthält.  
  
5.  Die Initialisierung mit einem Ausdruck, der weder eine Konstante noch ein Symbol ist.