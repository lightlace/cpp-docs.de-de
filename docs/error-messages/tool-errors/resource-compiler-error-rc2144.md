---
title: 'Ressourcencompiler: Fehler RC2144 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2144
dev_langs: C++
helpviewer_keywords: RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c29a1c1f392372b8dfddd84fa9693010e6a52bfa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2144"></a>Ressourcencompiler: Fehler RC2144
Primäre Sprach-ID ist keine Zahl  
  
 Primäre Sprach-ID muss eine hexadezimale Sprachen-ID sein. Finden Sie unter [Sprach- und Länder-/Regionszeichenfolgen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) in der *Run-Time Library Reference* eine Liste der gültigen Sprach-IDs.  
  
 Dieser Fehler kann auch auftreten, wenn Sie Ressourcen hinzugefügt und aus der.RC-Datei mithilfe des Tools gelöscht haben. Um dieses Problem zu beheben, öffnen Sie die.RC-Datei in einem Texteditor und bereinigen Sie manuell alle nicht verwendeten Ressourcen.