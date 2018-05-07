---
title: Neuverteilen von Webclientanwendungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92bd843b24ee13b3d606ba8bb4f4f1cc265e8e5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-web-client-applications"></a>Neuverteilen von Webclientanwendungen
Wenn Ihre Anwendung die MFC-Klassen implementieren das WebBrowser-Steuerelement verwendet (z. B. `CHtmlView` oder `CHtmlEditView`), Microsoft Internet Explorer 4.0 oder höher muss auf dem Zielcomputer mindestens minimal installiert.  
  
 Installieren der neuesten Version von Internet Explorer wird auch sichergestellt, dass der Zielcomputer über die neuesten allgemeine Benutzersteuerelement-Dateien verfügt.  
  
 Informationen zum Installieren von Internet Explorer-Komponenten, die minimalen steht in den folgenden Knowledge Base-Artikel:  
  
-   Q185375, so wird's gemacht: Erstellen eine einzelnen EXE-Installation von InternetExplorer ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))  
  
 Sie finden Knowledge Base-Artikel in der MSDN Library oder unter [ http://support.microsoft.com ](http://support.microsoft.com).  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellen von Desktopanwendungen](../ide/deploying-native-desktop-applications-visual-cpp.md)