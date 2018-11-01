---
title: Einstiegspunkte für exportierte DLL-Funktionen
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
ms.openlocfilehash: 8b84209833fee42ec8ebdd1fdea7a9229decad9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463323"
---
# <a name="exported-dll-function-entry-points"></a>Einstiegspunkte für exportierte DLL-Funktionen

Verwenden Sie für die exportierten Funktionen der DLL, die [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) Makro, um den richtigen globalen Status verwalten, beim Wechseln von der DLL-Modul zu DLL der aufrufenden Anwendung.

Wenn aufgerufen, um dieses Makro legt `pModuleState`, ein Zeiger auf ein `AFX_MODULE_STATE` Struktur, die globale Daten für das Modul als den effektiven Modulstatus für den Rest des enthaltenden Bereichs der Funktion enthält. Beim Verlassen des Bereichs, der das Makro enthält, wird der vorherige Modulstatus der effektiven automatisch wiederhergestellt.

Dieser Wechsel erfolgt durch Erstellen einer Instanz von einem `AFX_MODULE_STATE` -Klasse auf den Stapel. In seinem Konstruktor dieser Klasse erhält einen Zeiger auf den aktuellen Zustand in einer Membervariablen gespeichert und legt dann `pModuleState` als den neuen gültigen Modulstatus. In seinem Destruktor stellt diese Klasse in der Membervariablen als den effektiven Modulstatus gespeicherten Zeigers wieder her.

Wenn Sie eine exportierte Funktion, z. B. ein verfügen, die ein Dialogfeld, in der DLL, gestartet wird, müssen Sie den folgenden Code am Anfang der Funktion hinzufügen:

[!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]

Dies tauscht den aktuellen Modulstatus mit dem Status von zurückgegebenen [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) bis zum Ende des aktuellen Gültigkeitsbereichs.

Probleme mit den Ressourcen-DLLs werden auftreten, wenn die `AFX_MANAGE_STATE` Makro wird nicht verwendet. Standardmäßig verwendet MFC Ressourcenhandle von der hauptanwendung beim Laden der Ressourcenvorlage an. Mit dieser Vorlage wird in der DLL tatsächlich gespeichert. Die Ursache ist, dass MFC modulstatusinformationen nicht durch gewechselt wurde die `AFX_MANAGE_STATE` Makro. Das Ressourcenhandle wird von MFCs-Modulstatus wiederhergestellt. Wechseln nicht den Zustand bewirkt, dass das Handle falsche Ressource verwendet werden.

`AFX_MANAGE_STATE` muss nicht in jeder Funktion in der DLL eingefügt werden. Z. B. `InitInstance` aufgerufen werden kann, mit dem MFC-Code in die Anwendung ohne `AFX_MANAGE_STATE` Da MFC automatisch den Zustand vor dem verschiebt `InitInstance` und klicken Sie dann die Switches, die sie wieder nach `InitInstance` zurückgibt. Dasselbe gilt für alle meldungszuordnung Handler. Reguläre MFC-DLLs haben eine besondere master Fensterprozedur, die den Zustand automatisch wechselt vor dem Weiterleiten einer Nachricht.

## <a name="see-also"></a>Siehe auch

[Verwalten der Statusdaten von MFC-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)

