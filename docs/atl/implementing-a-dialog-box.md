---
title: Implementieren eines Dialogfelds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30e843c6df70548257de1bf1af8c5f0e83555652
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234061"
---
# <a name="implementing-a-dialog-box"></a>Implementieren eines Dialogfelds

Es gibt zwei Möglichkeiten, ein Dialogfeld, das dem ATL-Projekt hinzuzufügen: Verwenden Sie den ATL-Dialogfeld-Assistenten oder manuell hinzufügen.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>Hinzufügen eines Dialogfelds mit der ATL-Dialogfeld-Assistent

In der [Dialogfeld Klasse hinzufügen](../ide/add-class-dialog-box.md), wählen Sie das Objekt ATL-Dialogfeld, um ein Dialogfeld, das einem ATL-Projekt hinzu. Geben Sie die ATL-Dialogfeld-Assistent nach Bedarf, und klicken Sie auf **Fertig stellen**. Der Assistent fügt eine Klasse, die von abgeleiteten [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) zu Ihrem Projekt. Öffnen Sie **Ressourcenansicht** aus der **Ansicht** , suchen Sie das Dialogfeld, und doppelklicken Sie darauf, um sie im Ressourcen-Editor zu öffnen.

> [!NOTE]
>  Wenn das Dialogfeld von abgeleitet ist `CAxDialogImpl`, können sie beide ActiveX hosten und Windows-Steuerelemente. Wenn Sie in Ihre Dialogfeldklasse nicht den Aufwand für das ActiveX-Steuerelemente unterstützen möchten, verwenden Sie [CSimpleDialog](../atl/reference/csimpledialog-class.md) oder [CDialogImpl](../atl/reference/cdialogimpl-class.md) stattdessen.

Nachricht und Ereignishandler können aus der Klassenansicht auf die Dialogfeldklasse hinzugefügt werden. Weitere Informationen finden Sie unter [Hinzufügen eines ATL-Meldungshandlers](../atl/adding-an-atl-message-handler.md).

## <a name="adding-a-dialog-box-manually"></a>Das Dialogfeld hinzuzufügen manuell.

Implementieren eines Dialogfelds ähnelt der Implementieren eines Fensters. Leiten Sie eine Klasse entweder [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md), oder [CSimpleDialog](../atl/reference/csimpledialog-class.md) und deklarieren eine [meldungszuordnung](../atl/message-maps-atl.md) , Nachrichten zu verarbeiten. Allerdings müssen Sie auch eine Ressourcen-ID für Dialogfeld-Vorlage in der abgeleiteten Klasse angeben. Die Klasse müssen einen Datenmember namens `IDD` , diesen Wert enthalten soll.

> [!NOTE]
>  Bei der Erstellung eines Dialogfelds mithilfe der ATL-Dialogfeld-Assistent fügt der Assistent automatisch die `IDD` Member wie ein **Enum** Typ.

`CDialogImpl` können Sie implementieren ein modales oder ein nicht modales Dialogfeld an, das Windows-Steuerelemente hostet. `CAxDialogImpl` können Sie implementieren ein modales oder ein nicht modales Dialogfeld an, das sowohl Windows als auch ActiveX-Steuerelemente hostet.

Um ein modales Dialogfeld erstellen möchten, erstellen Sie eine Instanz von Ihr `CDialogImpl`-abgeleitet (oder `CAxDialogImpl`-abgeleitete) Klasse und rufen Sie dann die [DoModal](../atl/reference/cdialogimpl-class.md#domodal) Methode. Um ein modales Dialogfeld zu schließen, rufen Sie die [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) Methode aus einem Meldungshandler. Rufen Sie zum Erstellen eines nicht modalen Dialogfelds die [erstellen](../atl/reference/cdialogimpl-class.md#create) Methode anstelle von `DoModal`. Aufrufen, um ein nicht modales Dialogfeld zu zerstören, [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).

Auffangen von Ereignissen erfolgt automatisch im [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md). Implementieren Sie Meldungshandler des Dialogfelds aus, wie die Handler in einer `CWindowImpl`-abgeleitete Klasse. Bei ein Message-spezifische Wert zurückgegeben wird, die zurückgegeben werden, als ein `LRESULT`. Das zurückgegebene `LRESULT` Werte von ATL für die ordnungsgemäße Behandlung durch den Windows-Dialogfeld-Manager zugeordnet sind. Weitere Informationen finden Sie unter den Quellcode für [CDialogImplBaseT:: DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) in atlwin.h aufgetreten.

## <a name="example"></a>Beispiel

Die folgende Klasse wird ein Dialogfeld implementiert:

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>Siehe auch

[Fensterklassen](../atl/atl-window-classes.md)

