---
title: Implementieren eines Fensters mit CWindowImpl
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: 265c3145d8ceacae540286f72939dc046e7c8b35
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818075"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Implementieren eines Fensters mit CWindowImpl

Um ein Fenster zu implementieren, leiten Sie eine Klasse von `CWindowImpl`. Deklarieren Sie in der abgeleiteten Klasse einer meldungszuordnung und die Meldungshandlerfunktionen aus. Sie können nun Ihre Klasse auf drei verschiedene Arten verwenden:

- [Erstellen Sie ein Fenster, die basierend auf einer neuen Windows-Klasse](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Übergeordnete Klasse einer vorhandenen Windows-Klasse](#_atl_superclassing_an_existing_windows_class)

- [Ein vorhandenes Fenster-Unterklasse](#_atl_subclassing_an_existing_window)

##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Erstellen eines Fensters, das basierend auf einer neuen Windows-Klasse

`CWindowImpl` enthält die [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) Makro zum Deklarieren von Klasseninformationen für Windows. Dieses Makro implementiert die `GetWndClassInfo` -Funktion, die verwendet [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) die Informationen zu einer neuen Windows-Klasse definieren. Wenn `CWindowImpl::Create` aufgerufen wird, wird dieser Windows-Klasse registriert und ein neues Fenster erstellt wird.

> [!NOTE]
>  `CWindowImpl` übergeben Sie NULL, um die `DECLARE_WND_CLASS` Makro, das bedeutet, dass ATL generiert einen Windows-Klassennamen. Um einen eigenen Namen anzugeben, übergeben Sie eine Zeichenfolge an DECLARE_WND_CLASS in Ihre `CWindowImpl`-abgeleitete Klasse.

## <a name="example"></a>Beispiel

Es folgt ein Beispiel für eine Klasse, die ein Fenster, die basierend auf einer neuen Windows-Klasse implementiert:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Um ein Fenster zu erstellen, erstellen Sie eine Instanz von `CMyWindow` und rufen Sie dann die `Create` Methode.

> [!NOTE]
>  Um die Standard-Windows-Klasseninformationen überschreiben möchten, implementieren die `GetWndClassInfo` -Methode in der abgeleiteten Klasse durch Festlegen der `CWndClassInfo` Mitglieder auf die entsprechenden Werte.

##  <a name="_atl_superclassing_an_existing_windows_class"></a> Erstellung einer übergeordneten Klasse einer vorhandenen Windows-Klasse

Die [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) Makro können Sie beim Erstellen eines Fensters, eine übergeordnete Klasse für eine vorhandene Windows Klasse. Geben Sie dieses Makro in Ihre `CWindowImpl`-abgeleitete Klasse. Wie alle anderen ATL-Fenster werden Nachrichten von einer meldungszuordnung behandelt.

Wenn Sie DECLARE_WND_SUPERCLASS verwenden, wird eine neue Windows-Klasse registriert. Diese neue Klasse wird die vorhandene Klasse, die Sie angeben, aber ersetzt die Fensterprozedur mit identisch sein `CWindowImpl::WindowProc` (oder mit Ihrer Funktion, die diese Methode überschreibt).

## <a name="example"></a>Beispiel

Folgende ist ein Beispiel für eine Klasse, eine übergeordnete Klasse der standardmäßigen Edit Klasse:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Um das Bearbeitungsfenster zu erstellen, erstellen Sie eine Instanz von `CMyEdit` und rufen Sie dann die `Create` Methode.

##  <a name="_atl_subclassing_an_existing_window"></a> Erstellen von Unterklassen für ein vorhandenes Fenster

Um eine Unterklasse ein vorhandenes Fenster, leiten Sie eine Klasse von `CWindowImpl` und eine meldungszuordnung, wie in den beiden vorherigen Fällen deklarieren. Beachten Sie jedoch, dass Sie alle Informationen für den Windows-Klasse, da Sie Unterklasse ein bereits vorhandenes Fenster werden nicht angeben.

Statt `Create`, rufen Sie `SubclassWindow` und übergeben sie das Handle zum vorhandenen Fenster Unterklasse werden sollen. Nachdem das Fenster als Unterklasse definiert ist, verwenden sie `CWindowImpl::WindowProc` (oder die Funktion, den diese Methode überschreibt) zum Weiterleiten von Nachrichten an die meldungszuordnung. Um ein untergeordnetes Fenster von Ihrem Objekt trennen möchten, rufen Sie `UnsubclassWindow`. Die ursprüngliche Fensterprozedur von Windows wird wiederhergestellt.

## <a name="see-also"></a>Siehe auch

[Implementieren eines Fensters](../atl/implementing-a-window.md)
