---
title: 'Ressourcencompiler: Fehler RC2001 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2001
dev_langs: C++
helpviewer_keywords: RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c04110898780495f918c1e37c0068daead340a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2001"></a>Ressourcencompiler: Fehler RC2001
Zeilenvorschub in Konstante.  
  
 Eine Zeichenfolgenkonstante wurde in einer zweiten Zeile ohne einen umgekehrten Schrägstrich fortgesetzt (**\\**) oder geschlossen, und öffnen doppelte Anführungszeichen (**"**).  
  
 Führen Sie eine der folgenden Schritte aus, um eine Zeichenfolgenkonstante zu unterbrechen, die in zwei Zeilen in der Quelldatei ist:  
  
-   Beenden Sie die erste Zeile mit dem Zeilenfortsetzungszeichen ein umgekehrter Schrägstrich.  
  
-   Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie die Zeichenfolge in der nächsten Zeile ein weiteres Anführungszeichen voranstellen.  
  
 Es ist nicht ausreichend, um die erste Zeile mit \n die Escapesequenz für das Einbetten von ein neue Zeilenumbruchzeichen in eine Zeichenfolgenkonstante zu beenden.