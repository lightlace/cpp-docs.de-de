---
title: "Unterstützte Plattformen (Visual C++) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 0192e9bd6ef9d93e274c43c24137a27e5aa53dab
ms.openlocfilehash: c0c209c16ad4a264b851321a2879104112da81f2
ms.lasthandoff: 02/24/2017

---
# <a name="supported-platforms-visual-c"></a>Unterstützte Plattformen (Visual C++)
Die Apps, die mit [!INCLUDE[vsprvs](assembler/masm/includes/vsprvs_md.md)] erstellt werden, können folgendermaßen für verschiedene Plattformen eingesetzt werden.  
  
|Betriebssystem|x86|x64|ARM|  
|----------------------|---------|---------|---------|  
|Windows XP|X*|X*||  
|[!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]|X*|X*||  
|Windows Vista|X|X||  
|Windows Server 2008|X|X||  
|Windows 7|X|X||  
|Windows Server 2012 R2|X|X||  
|Windows 8|X|X|X|  
|Windows 8.1|X|X|X|  
|Windows 10|X|X|X|  
|Android **|X|X|X|  
|iOS **|X|X|w|  
  
 \* Sie können das in Visual Studio 2015, Visual Studio 2013 und Visual Studio 2012 Update 1 oder höher enthaltene Windows XP-Plattformtoolset zum Erstellen von Windows XP- und [!INCLUDE[WinXPSvr](build/includes/winxpsvr_md.md)]-Projekten verwenden. Weitere Informationen zum Verwenden dieses Plattformtoolsets finden Sie unter [Konfigurieren von C++11-Programmen für Windows XP](build/configuring-programs-for-windows-xp.md). Weitere Informationen zum Ändern des Plattformtoolsets finden Sie unter [Vorgehensweise: Ändern des Zielframeworks und des Plattformtoolsets](build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
 ** Sie können die optionale Visual C++ für plattformübergreifende Mobil-Entwicklungskomponente im Visual Studio 2015-Setup verwenden, um auf IOS-oder Android-Plattformen abgezielte Apps zu entwickeln. Weitere Informationen finden Sie unter [Installieren von Visual C++ für die plattformübergreifende mobile Entwicklung](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). Um iOS-Code zu erstellen, müssen Sie einen Macintosh-Computer besitzen und weitere Anforderungen erfüllen. Eine Liste der Voraussetzungen und Installationsanweisungen finden Sie unter [Installieren und Konfigurieren von Tools zum Erstellen mit iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Sie können x86- oder ARM-Code für die Zielhardware erstellen. Verwenden Sie x86-Konfigurationen zum Entwickeln für den iOS-Simulator, Microsoft Visual Studio-Emulator für Android und einige Android-Geräte. Verwenden Sie ARM-Konfigurationen für iOS-Geräte und die meisten Android-Geräte.  
  
 Informationen zum Festlegen der Zielplattformkonfiguration finden Sie unter [Vorgehensweise: Konfigurieren von Visual C++ Projekten für 64-Bit-Zielplattformen](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual C++ Tools and Features in Visual Studio Editions (Visual C++-Tools und -Funktionen in Visual Studio-Editionen)](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)   
 [Erste Schritte](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)
