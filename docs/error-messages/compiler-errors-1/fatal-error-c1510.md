---
title: Schwerwiegender Fehler C1510 | Microsoft Docs
ms.custom: 
ms.date: 04/11/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1510
dev_langs:
- C++
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
caps.latest.revision: 1
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 373cd74b1649fb9c1bd87cad1903df183f153c0f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1510"></a>Schwerwiegender Fehler C1510
Die Sprachressourcendatei "clui.dll" kann nicht geöffnet werden.  
  
 Der Compiler kann die Language-Ressourcen-DLL nicht laden.  
  
Es gibt zwei häufige Ursachen für dieses Problem. Wenn Sie die 32-Bit-Compiler und Tools zu verwenden, Sie dieser Fehler können bei großen Projekten angezeigt, die mehr als 2 GB Arbeitsspeicher bei einen Link zu verwenden. Eine mögliche Lösung auf 64-Bit-Windows-Systemen ist das systemeigene 64-Bit-oder cross-Compiler und Tools zum Generieren von Code. Dies nutzt den größeren belegten Speicherplatz für 64-Bit-apps verfügbar. Wenn Sie einen 32-Bit-Compiler verwenden müssen, weil Sie auf einem 32-Bit-System ausgeführt werden, können Sie in einigen Fällen die Menge an Arbeitsspeicher für den Linker an, / 3 GB erhöhen. Weitere Informationen finden Sie unter [4 Gigabyte Tuning: "bcdedit" und "Boot.ini"](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) und ["bcdedit" / set Increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) Befehl.  

Die andere häufige Ursache ist eine Visual Studio-Installation beschädigt oder unvollständig. In diesem Fall führen Sie das Installationsprogramm erneut aus, um reparieren oder neu installieren von Visual Studio.  
  
