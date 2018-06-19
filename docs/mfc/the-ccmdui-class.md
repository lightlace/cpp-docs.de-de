---
title: Die CCmdUI-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dde8c31620f64e6201c59b7031c789caa16c4902
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379807"
---
# <a name="the-ccmdui-class"></a>Die CCmdUI-Klasse
Wenn er einen Aktualisierungsbefehl an seinen Handler weitergeleitet wird, das Framework übergibt dem Handler einen Zeiger auf eine `CCmdUI` Objekt (oder auf ein Objekt des eine `CCmdUI`-abgeleitete Klasse). Dieses Objekt darstellt, Menüs oder Symbolleisten-Schaltflächen oder anderen Benutzeroberfläche-Objekt, das der Befehl generiert. Vom updatehandler Ruft die Memberfunktionen von der `CCmdUI` -Struktur durch den Zeiger auf das Objekt für die Benutzeroberfläche zu aktualisieren. Hier ist z. B. ein updatehandler für das Menüelement alle löschen:  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Dieser Handler Ruft die **aktivieren** Memberfunktion eines Objekts mit Zugriff auf das Menüelement. **Aktivieren Sie** ist das Element zur Verwendung verfügbar.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)

