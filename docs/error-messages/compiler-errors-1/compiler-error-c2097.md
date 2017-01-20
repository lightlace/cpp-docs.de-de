---
title: "Compilerfehler C2097"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2097"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2097"
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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