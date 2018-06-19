---
title: Befehlszeilenfehler D8016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8016
dev_langs:
- C++
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6f9709da189403f2594d76751430d30554bffe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300617"
---
# <a name="command-line-error-d8016"></a>Befehlszeilenfehler D8016
'Option 1' und 'option2' Befehlszeilenoptionen sind nicht kompatibel  
  
 Die Befehlszeilenoptionen können nicht zusammen angegeben werden.  
  
 Überprüfen Sie die Umgebungsvariablen wie z. B. CL, Optionsangaben.  
  
 **"/ CLR"** impliziert **/EHa**, und Sie können angeben, alle anderen **/EH** Compileroption mit **"/ CLR"**. Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Möglicherweise wird bei der Aktualisierung die Meldung D8016 eine [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0-Projekt: des Projekt-Assistent Updatevorgangs möglicherweise ermöglichen **/RTC** für jede Quelle-Codedatei im Projekt, überschreibt die der **/RTC** Einstellung für die Projekt.  Ändern Sie zur Behebung der **/RTC** für jede Quelle-Codedatei im Projekt auf die Standardeinstellung festlegen, d. h. die projekteinstellung für **/RTC** wird für jede Datei wirksam werden.  
  
 Finden Sie unter [/RTC (Run-Time Checks Fehler)](../../build/reference/rtc-run-time-error-checks.md) Informationen zum Ändern der **/RTC** Einstellung der Eigenschaft.