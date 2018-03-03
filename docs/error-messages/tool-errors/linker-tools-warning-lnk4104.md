---
title: Linkertoolwarnung Lnk4104 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b26286f375f54a20e1d3db534576f692179ade24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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