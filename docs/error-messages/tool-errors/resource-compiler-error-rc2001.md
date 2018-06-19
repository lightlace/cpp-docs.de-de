---
title: 'Ressourcencompiler: Fehler RC2001 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef1fd5d29fc5784ee418a8456cacec37e943b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322418"
---
# <a name="resource-compiler-error-rc2001"></a>Ressourcencompiler: Fehler RC2001
Zeilenvorschub in Konstante.  
  
 Eine Zeichenfolgenkonstante wurde in einer zweiten Zeile ohne einen umgekehrten Schrägstrich fortgesetzt (**\\**) oder geschlossen, und öffnen doppelte Anführungszeichen (**"**).  
  
 Führen Sie eine der folgenden Schritte aus, um eine Zeichenfolgenkonstante zu unterbrechen, die in zwei Zeilen in der Quelldatei ist:  
  
-   Beenden Sie die erste Zeile mit dem Zeilenfortsetzungszeichen ein umgekehrter Schrägstrich.  
  
-   Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie die Zeichenfolge in der nächsten Zeile ein weiteres Anführungszeichen voranstellen.  
  
 Es ist nicht ausreichend, um die erste Zeile mit \n die Escapesequenz für das Einbetten von ein neue Zeilenumbruchzeichen in eine Zeichenfolgenkonstante zu beenden.