---
title: Mathematischer Fehler M6108 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfeca48aa04ebfbc097649e5c25253166c50dad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6108"></a>Mathematischer Fehler M6108
Quadratwurzel  
  
 Der Operand in einem Vorgang Quadratwurzel war negativ.  
  
 Programm mit Exitcode 136 beendet wird.  
  
> [!NOTE]
>  Die `sqrt` Funktion in der C-Laufzeitbibliothek und die FORTRAN-Funktion **SQRT** generieren Sie diesen Fehler nicht. Das C `sqrt` Funktion prüft das Argument vor dem Ausführen des Vorgangs und gibt einen Fehlerwert zurück, wenn der Operand negativ ist. Die FORTRAN **SQRT** Funktion generiert die Domänenfehler [M6201](../../error-messages/tool-errors/math-error-m6201.md) statt diesen Fehler.