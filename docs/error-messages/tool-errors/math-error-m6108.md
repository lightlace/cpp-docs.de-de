---
title: Mathematischer Fehler M6108 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6108
dev_langs: C++
helpviewer_keywords: M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6db123d9cb96274848a3edd9f845f86f413d8e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6108"></a>Mathematischer Fehler M6108
Quadratwurzel  
  
 Der Operand in einem Vorgang Quadratwurzel war negativ.  
  
 Programm mit Exitcode 136 beendet wird.  
  
> [!NOTE]
>  Die `sqrt` Funktion in der C-Laufzeitbibliothek und die FORTRAN-Funktion **SQRT** generieren Sie diesen Fehler nicht. Das C `sqrt` Funktion prüft das Argument vor dem Ausführen des Vorgangs und gibt einen Fehlerwert zurück, wenn der Operand negativ ist. Die FORTRAN **SQRT** Funktion generiert die Domänenfehler [M6201](../../error-messages/tool-errors/math-error-m6201.md) statt diesen Fehler.