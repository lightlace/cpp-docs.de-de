---
title: Neuverteilen von Webclientanwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
ms.openlocfilehash: a2af5bfe4e3323f14fc939a6e33cb7bd2b501652
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744629"
---
# <a name="redistributing-web-client-applications"></a>Neuverteilen von Webclientanwendungen

Wenn Ihre Anwendung die MFC-Klassen verwendet, die das WebBrowser-Steuerelement implementieren (z.B. `CHtmlView` oder `CHtmlEditView`), muss mindestens Microsoft Internet Explorer 4.0 oder höher auf dem Zielcomputer installiert sein.

Durch das Installieren der neuesten Version von Internet Explorer wird ebenfalls sichergestellt, dass der Zielcomputer über die aktuellsten allgemeinen Steuerelementdateien verfügt. Weitere Informationen finden Sie unter [Installieren und Bereitstellen von Internet Explorer 11](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11).

## <a name="see-also"></a>Siehe auch

[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)
