---
title: Windows-Plattformen (CRT) | Microsoft-Dokumentation
ms.custom: 
ms.date: 02/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility [C++], C run-time libraries
- compatibility [C++], C run-time libraries
- MBCS [C++], Win32 platforms
- operating systems [C++]
- Unicode [C++], Win32 platforms
ms.assetid: 0aacaf45-6dc4-4908-bd52-57abac7b39f6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a5e7898cad7120333bd0549a44931d9e23640c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="windows-platforms-crt"></a>Windows-Plattformen (CRT)

Die C-Laufzeitbibliotheken für Visual Studio unterstützen die aktuellen Versionen von Windows und Windows Server, [!INCLUDE[win8](../build/reference/includes/win8_md.md)], [!INCLUDE[winserver8](../build/reference/includes/winserver8_md.md)], [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/reference/includes/winsvr08_md.md)], und Windows Vista, optional unterstützen sie [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 (SP3) für x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 (SP2) für x64 und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 (SP2) für x86 und x64. All diese Betriebssysteme unterstützen die Windows-Desktop-API (Win32) und Unicode. Darüber hinaus kann jede Win32-Anwendung einen Multibyte-Zeichensatz (Multibyte Character Set, MBCS) verwenden.

> [!NOTE]
> Die Standardinstallation der Workload **Desktopentwicklung mit C++** in Visual Studio 2017 bietet keine Unterstützung für die Entwicklung mit [!INCLUDE[winxp](../build/includes/winxp_md.md)] und [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Sie müssen die optionale Komponente **Windows XP-Unterstützung für C++** installieren, um ein Windows XP-Plattformtoolset zu aktivieren.

## <a name="see-also"></a>Siehe auch

[Kompatibilität](../c-runtime-library/compatibility.md)  
