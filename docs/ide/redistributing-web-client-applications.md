---
title: Neuverteilen von Webclientanwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
ms.openlocfilehash: 37ff666493ada7dada19f5731e6581603d3cb57e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512414"
---
# <a name="redistributing-web-client-applications"></a>Neuverteilen von Webclientanwendungen

Wenn Ihre Anwendung die MFC-Klassen verwendet, die das WebBrowser-Steuerelement implementieren (z.B. `CHtmlView` oder `CHtmlEditView`), muss mindestens Microsoft Internet Explorer 4.0 oder höher auf dem Zielcomputer installiert sein.

Durch das Installieren der neuesten Version von Internet Explorer wird ebenfalls sichergestellt, dass der Zielcomputer über die aktuellsten allgemeinen Steuerelementdateien verfügt. Weitere Informationen finden Sie unter [Installieren und Bereitstellen von Internet Explorer 11](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11).

## <a name="see-also"></a>Siehe auch

[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)