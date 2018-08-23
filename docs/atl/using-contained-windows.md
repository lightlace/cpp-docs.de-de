---
title: Verwenden eigenständige Windows | Microsoft-Dokumentation
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
ms.openlocfilehash: 64a2f9d5d296e28b4b773e072edc90e1b339feae
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42573329"
---
# <a name="using-contained-windows"></a>Verwenden eigenständige Windows
ATL implementiert enthaltene Fenstern mit [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md). Eine im Fenster ein Fenster darstellt, das ihrer Nachrichten in einem Container-Objekt nicht in ihrer eigenen Klasse delegiert.  
  
> [!NOTE]
>  Sie müssen nicht Ableiten einer Klasse von `CContainedWindowT` um enthaltenen Fenstern zu verwenden.  
  
 Mit eigenständigen Windows können Sie einer übergeordnete Klasse, einer vorhandenen Windows-Klasse oder ein vorhandenes Fenster-Unterklasse. Beim Erstellen eines Fensters, eine übergeordnete Klasse für eine vorhandene Windows Klasse, geben Sie zuerst den vorhandenen Klassennamen im Konstruktor für die `CContainedWindowT` Objekt. Rufen Sie anschließend `CContainedWindowT::Create`. Um eine Unterklasse ein vorhandenes Fenster müssen Sie einen Namen für Windows-Klasse (übergeben Sie NULL an den Konstruktor) angeben. Rufen Sie einfach die `CContainedWindowT::SubclassWindow` Methode mit dem Handle des Fensters in Unterklassen unterteilt wird.  
  
 Normalerweise verwenden Sie eigenständige Windows als Datenmember einer Container-Klasse. Der Container muss es sich nicht um ein Fenster sein; Sie muss jedoch von abgeleitet [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Ein enthaltenes Fensters kann alternativen meldungszuordnungen verwenden, um Nachrichten zu verarbeiten. Wenn Sie mehr als einem eigenständigen Fenster verfügen, sollten Sie deklarieren, dass mehrere meldungszuordnungen, die jeweils entsprechenden auf einem separaten eigenständigen Fenster wechseln.  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel für eine Container-Klasse mit zwei eigenständige Windows:  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]  
  
 Weitere Informationen zu den enthaltenen Fenstern, finden Sie unter den [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)

