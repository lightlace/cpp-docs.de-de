---
title: Verwenden von eigenständigen Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6c3b439baf05c4e4287613e9b6b5a9b1c2546b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357920"
---
# <a name="using-contained-windows"></a>Eigenständige Windows verwenden
ATL implementiert enthaltene Windows mit [CContainedWindow](../atl/reference/ccontainedwindowt-class.md). Ein enthaltenes Fenster stellt ein Fenster, das ihrer Nachrichten in ein Container-Objekt nicht in eine eigene Klasse delegiert.  
  
> [!NOTE]
>  Sie müssen nicht Ableiten einer Klasse von `CContainedWindowT` um eigenständige Windows verwenden.  
  
 Mit eigenständigen Windows können Sie einer übergeordnete Klasse, einer vorhandenen Windows-Klasse oder ein vorhandenes Fenster-Unterklasse. Beim Erstellen eines Fensters, das einer vorhandenen Windows Klasse, geben Sie zuerst die vorhandene Klassennamen im Konstruktor für die `CContainedWindowT` Objekt. Rufen Sie anschließend `CContainedWindowT::Create`. Um ein vorhandenes Fenster-Unterklasse, müssen Sie keinen Windows-Klassennamen angeben (übergeben Sie **NULL** an den Konstruktor). Rufen Sie einfach die `CContainedWindowT::SubclassWindow` Methode mit dem Handle für das Fenster wird als Unterklasse.  
  
 Normalerweise verwenden Sie eigenständige Windows als Datenmember einer Container-Klasse. Der Container muss kein Fenster werden; Allerdings müssen Sie sich von abgeleitet [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Ein enthaltenen Fensters kann alternative meldungszuordnungen verwenden, die Nachrichten zu verarbeiten. Wenn Sie mehr als ein eigenständigen Fenster verfügen, sollten mehrere meldungszuordnungen, die jeweils entsprechenden auf einem separaten enthaltenen Fenster alternativer deklariert werden.  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel für eine Containerklasse mit zwei eigenständige Windows:  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 Weitere Informationen zu eigenständigen Fenstern finden Sie unter der [SUBEDIT](../visual-cpp-samples.md) Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)

