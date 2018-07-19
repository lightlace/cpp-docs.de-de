---
title: Schwerwiegender Fehler C1099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1099
dev_langs:
- C++
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d97bed1bdc81c738ff20bb85038153181ddb06ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198780"
---
# <a name="fatal-error-c1099"></a>Schwerwiegender Fehler C1099
Kompilierungsabbruch durch Modul für Bearbeiten und Fortfahren  
  
 Durch Bearbeiten und Fortfahren wurde eine vorkompilierte Headerdatei in Vorbereitung für das Kompilieren von Codeänderungen geladen, aber nachfolgende Maßnahmen (z. B. Codeänderungen vor der vorkompilierten `#include` -Headeranweisung oder das Beenden des Debuggers) verhindern, dass die Kompilierung mit diesem Prozess von „Bearbeiten und Fortfahren“ beendet wird. Sie müssen keine Maßnahmen ergreifen, um diesen Fehler zu beheben.