---
title: Exportierte DLL-Funktion Einstiegspunkte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8e9ff08054fbef3f15283395d7eb150551926dc
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928624"
---
# <a name="exported-dll-function-entry-points"></a>Einstiegspunkte für exportierte DLL-Funktionen
Bei exportierten Funktionen einer DLL verwenden, die [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) Makro, um den ordnungsgemäßen globalen Status beizubehalten, beim Wechsel vom DLL-Modul zur DLL der aufrufenden Anwendung.  
  
 Beim Aufrufen dieses Makro legt `pModuleState`, ein Zeiger auf eine `AFX_MODULE_STATE` Struktur, die globale Daten für das Modul als effektiver Modulstatus für den Rest des enthaltenden Bereichs der Funktion enthält. Beim Verlassen des Bereichs, die das Makro enthält, wird die vorherige effektive Modulstatus automatisch wiederhergestellt.  
  
 Dieser Wechsel erfolgt durch Erstellen einer Instanz von einer `AFX_MODULE_STATE` Klasse auf dem Stapel. In seinem Konstruktor dieser Klasse erhält einen Zeiger auf den aktuellen Zustand und speichert ihn in einer Membervariablen gespeichert, und legt dann `pModuleState` als den neuen gültigen Modulstatus. In seinem Destruktor stellt diese Klasse die in ihrer Membervariablen als die effektive Modulstatus gespeicherten Zeiger wieder her.  
  
 Wenn Sie eine exportierte Funktion, z. B. einen verfügen, die ein Dialogfeld, in der DLL startet müssen Sie den folgenden Code am Anfang der Funktion hinzufügen:  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]  
  
 Dies tauscht den aktuellen Modulstatus mit dem Status Merry [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) bis zum Ende des aktuellen Gültigkeitsbereichs.  
  
 Probleme mit den Ressourcen-DLLs erfolgt, wenn die `AFX_MANAGE_STATE` Makro wird nicht verwendet. Standardmäßig verwendet MFC das Ressourcenhandle von der hauptanwendung, um die Ressourcenvorlage zu laden. Diese Vorlage wird tatsächlich in der DLL gespeichert. Die Ursache ist, dass MFC Modulzustandsinformationen nicht durch gewechselt wurde die `AFX_MANAGE_STATE` Makro. Das Ressourcenhandle wird vom MFC Modulstatus wiederhergestellt. Nicht durch einen Wechsel der Modulstatus wird das falsche Ressourcenhandle verwendet werden.  
  
 `AFX_MANAGE_STATE` muss nicht jede Funktion in der DLL abgelegt werden. Beispielsweise `InitInstance` kann aufgerufen werden, durch den MFC-Code in der Anwendung ohne `AFX_MANAGE_STATE` Da MFC automatisch den Zustand vor dem verlagert `InitInstance` und dann wieder nach Switches `InitInstance` zurückgibt. Dasselbe gilt für alle meldungszuordnung Handler. Reguläre MFC-DLLs haben eine spezielle master Fensterprozedur, die den Zustand automatisch wechselt vor dem Weiterleiten einer Nachricht.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

