---
title: Linkertoolwarnung Lnk4104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ea3e074cc0db9591cd0ffe9329ff7f1936563f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300952"
---
# <a name="linker-tools-warning-lnk4104"></a>Linkertoolwarnung LNK4104
Export von Symbol 'Symbol' sollten privat sein.  
  
 Die `symbol` kann eines der folgenden sein:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 Diese Warnung wird ausgegeben, wenn Sie eine Importbibliothek für eine DLL erstellen und Exportieren eine der oben genannten Funktionen ohne es als privat in der Moduldefinition Datei anzugeben. Im Allgemeinen werden diese Funktionen für die Verwendung nur durch OLE exportiert. Platzieren sie in der Importbibliothek kann auf ungewöhnliches Verhalten führen, wenn ein Programm nicht ordnungsgemäß mit der Bibliothek verknüpft diese aufgerufen wird. Weitere Informationen über die PRIVATE-Schlüsselwort finden Sie unter [EXPORTE](../../build/reference/exports.md).