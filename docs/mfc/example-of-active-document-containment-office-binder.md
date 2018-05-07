---
title: 'Beispiel für Active Document-Container: Office Binder | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7e4f82840a4c5620762ad57b5b9fa8dd7e62d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="example-of-active-document-containment-office-binder"></a>Beispiel für einen Active Document-Container: Office Binder
Die Microsoft Office Binder ist ein Beispiel für einen active Document-Container. Ein Office Binder umfasst zwei Hauptbereiche wie Container in der Regel. Der linke Bereich enthält die Symbole, die aktive Dokumente in den Binder entsprechen. Jedes Dokument wird aufgerufen, eine *Abschnitt* innerhalb der Binder. Ein Binder kann z. B. Word-Dokumenten, PowerPoint-Dateien, Excel-Kalkulationstabellen usw. enthalten.  
  
 Klicken auf ein Symbol im linken Bereich wird das entsprechende active Document aktiviert. Der rechte Bereich des Binders zeigt dann den Inhalt des aktuell ausgewählten aktiven Dokuments.  
  
 Wenn Sie zu öffnen, und aktivieren ein Word-Dokument in einen Binder, die Word-Menü- und Symbolleisten angezeigt werden, am oberen Rand der Ansichtsframe und können Sie den Inhalt des Dokuments mithilfe von Word-Befehle oder Tools bearbeiten. Die Menüleiste ist jedoch eine Kombination aus dem Binder und die Word Menüleisten. Schreibberechtigung Binder und Word **Hilfe** Menüs, den Inhalt der jeweiligen Menüs zusammengeführt werden. Active Document-Container, z. B. Office Binder automatisch bereitstellen **Hilfe** Menü zusammenführen; Weitere Informationen finden Sie unter [Zusammenführen von Hilfemenüs](../mfc/help-menu-merging.md).  
  
 Wenn Sie auswählen ein aktiven Dokuments von einer anderen Anwendungstyp, den Binder Schnittstelle-Änderungen an der Anwendungstyp für das aktive Dokument zu berücksichtigen. Ein Binder ein Excel-Arbeitsblatt enthält, werden Sie z. B. bemerken, dass die Menüs in den Binder zu ändern, wenn Sie im Abschnitt der Excel-Arbeitsblatt auswählen.  
  
 Es gibt natürlich anderen möglichen Arten von Containern neben Bindern. Datei-Explorer verwendet die typische zweiteiligen-Schnittstelle, die in der linke Bereich ein Strukturansicht-Steuerelement verwendet, um eine hierarchische Liste von Verzeichnissen in einem Laufwerk oder einem Netzwerk anzuzeigen, während der rechte Bereich im derzeit ausgewählten Verzeichnis enthaltenen Dateien zeigt. Ein Internet Browsertyp Container (z. B. Microsoft Internet Explorer), anstatt über eine Dual-Bereich-Schnittstelle in der Regel verfügt über einen einzelnen Frame und bereitstellt Navigation links verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)

