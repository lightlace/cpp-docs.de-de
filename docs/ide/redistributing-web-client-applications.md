---
title: Verteilen von Webclientanwendungen | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33323195"
---
# <a name="redistributing-web-client-applications"></a>Neuverteilen von Webclientanwendungen
Wenn Ihre Anwendung die MFC-Klassen verwendet, die das WebBrowser-Steuerelement implementieren (z.B. `CHtmlView` oder `CHtmlEditView`), muss mindestens Microsoft Internet Explorer 4.0 oder höher auf dem Zielcomputer installiert sein.  
  
 Durch das Installieren der neuesten Version von Internet Explorer wird ebenfalls sichergestellt, dass der Zielcomputer über die aktuellsten allgemeinen Steuerelementdateien verfügt.  
  
 Informationen über die Installation minimaler Internet Explorer-Komponenten finden Sie im folgenden Knowledge Base-Artikel:  
  
-   Q185375, HOWTO: Create a Single EXE Install of Internet Explorer (Vorgehensweise: Erstellen einer einzelnen EXE-Installation von Internet Explorer) ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))  
  
 Knowledge Base-Artikel finden Sie in der MSDN Library oder unter [http://support.microsoft.com](http://support.microsoft.com).  
  
## <a name="see-also"></a>Siehe auch  
 [Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)