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
ms.openlocfilehash: d036f7d46e0db84b8572b26c747947c929972517
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889931"
---
# <a name="redistributing-web-client-applications"></a>Neuverteilen von Webclientanwendungen

Wenn Ihre Anwendung die MFC-Klassen verwendet, die das WebBrowser-Steuerelement implementieren (z.B. `CHtmlView` oder `CHtmlEditView`), muss mindestens Microsoft Internet Explorer 4.0 oder höher auf dem Zielcomputer installiert sein.

Durch das Installieren der neuesten Version von Internet Explorer wird ebenfalls sichergestellt, dass der Zielcomputer über die aktuellsten allgemeinen Steuerelementdateien verfügt. Weitere Informationen finden Sie unter [Installieren und Bereitstellen von Internet Explorer 11](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11).

## <a name="see-also"></a>Siehe auch

[Deploying Desktop Applications (Bereitstellen von Desktopanwendungen)](../ide/deploying-native-desktop-applications-visual-cpp.md)