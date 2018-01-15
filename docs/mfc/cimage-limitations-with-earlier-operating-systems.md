---
title: "Einschränkungen für CImage in früheren Betriebssystemen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImage
dev_langs: C++
helpviewer_keywords: CImage class [MFC], limitations
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27046704975bf8f5e28f12acbfa72e860660fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-limitations-with-earlier-operating-systems"></a>Einschränkungen für CImage in früheren Betriebssystemen
Viele `CImage` Funktionen funktionieren nur mit neueren Versionen von Windows: Windows 95-und Windows 98 oder Windows NT 4.0 oder Windows 2000. Dieser Artikel beschreibt die Einschränkungen Version bestimmter Methoden.  
  
 [CImage::PlgBlt](../atl-mfc-shared/reference/cimage-class.md#plgblt) und [CImage::MaskBlt](../atl-mfc-shared/reference/cimage-class.md#maskblt) für nur Windows NT 4.0 oder höher. Sie funktionieren nicht in Anwendungen, die auf Windows 95-und Windows 98 oder höher ausgeführt werden.  
  
 [CImage::AlphaBlend](../atl-mfc-shared/reference/cimage-class.md#alphablend) und [CImage::TransparentBlt](../atl-mfc-shared/reference/cimage-class.md#transparentblt) für nur Windows 2000 oder höher und Windows 98 oder höher, da Sie eine Verknüpfung mit msimg32.lib diese Methoden müssen. (Diese Bibliothek ist verfügbar, die nur für Anwendungen, die unter Windows 2000 oder höher und Windows 98 oder höher.)  
  
 Sie können einschließen `AlphaBlend` und `TransparentBlt` in einer Anwendung, die unter Windows 95 oder Windows NT 4.0 ausgeführt wird, nur dann, wenn diese Methoden nicht aufgerufen werden. Wenn Ihre Anwendung diese Methoden enthält, und es unter früheren Betriebssystemen ausgeführt werden muss, müssen, verwenden Sie den Linker [/DELAYLOAD](../build/reference/delayload-delay-load-import.md) um das Laden von msimg32.lib zu verzögern. Solange die Anwendung eine der folgenden Methoden, während der Ausführung unter Windows NT 4.0 oder Windows 95 nicht aufgerufen wird, versucht es nicht msimg32.lib zu laden. Sie können überprüfen, ob Transparenz Unterstützung kann über die `CImage::IsTransparencySupported` Methode.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 Fügen Sie zum Kompilieren einer Anwendung, die diese Methoden aufruft, ein #define _WIN32_WINNT-Anweisung vor der #including alle Systemheader, die angeben, dass der Windows-Version 5.0 größer oder gleich ist:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 Wenn Ihre Anwendung nicht auf einem älteren Betriebssystem als Windows 2000 oder Windows 98 ausgeführt werden muss, können Sie direkt mit verknüpfen msimg32.lib ohne **/DELAYLOAD**.  
  
 [CImage::Draw](../atl-mfc-shared/reference/cimage-class.md#draw) verhält sich anders bei Verwendung mit Windows 2000 und Windows 98 als mit Windows NT 4.0 oder Windows 95.  
  
 Wenn Sie die Anwendung mit _WIN32_WINNT Satz an einen Wert kleiner als 0 x 0500, Kompilieren **zeichnen** wird, ist aber nicht verarbeitet Transparenz automatisch auf Systemen mit Windows 2000 und Windows 98 und höher.  
  
 Wenn Sie Ihre Anwendung mit _WIN32_WINNT auf 0 x 0500 festgelegt oder größer, Kompilieren **zeichnen** Transparenz automatisch auf Systemen mit Windows 2000 oder Windows 98 und höher werden verarbeitet. Sie funktioniert zudem, jedoch keine Unterstützung für die Transparenz mit Windows NT 4.0 oder Windows 95; Sie müssen allerdings verwenden **/DELAYLOAD** verzögert das Laden von msimg32. LIB, wie oben beschrieben `AlphaBlend` und `TransparentBlt`.  
  
## <a name="see-also"></a>Siehe auch  
 [CImage-Klasse](../atl-mfc-shared/reference/cimage-class.md)
