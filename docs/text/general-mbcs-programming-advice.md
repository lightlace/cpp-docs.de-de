---
title: Allgemeine Ratschläge für die MBCS-Programmierung
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
ms.openlocfilehash: 887387220105614eb3257f008ec601a6fc0adc18
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491186"
---
# <a name="general-mbcs-programming-advice"></a>Allgemeine Ratschläge für die MBCS-Programmierung

Verwenden Sie die folgenden Tipps:

- Verwenden Sie aus Gründen der Flexibilität Lauf Zeit Makros, `_tcschr` wie `_tcscpy` z. b. und, wenn möglich. Weitere Informationen finden Sie unter Zuordnungen für [generischen Text in Tchar. h](../text/generic-text-mappings-in-tchar-h.md).

- Verwenden Sie die C-Lauf `_getmbcp` Zeitfunktion, um Informationen zur aktuellen Codepage zu erhalten.

- Verwenden Sie keine Zeichen folgen Ressourcen. Abhängig von der Zielsprache hat eine gegebene Zeichenfolge möglicherweise eine andere Bedeutung, wenn Sie übersetzt wird. Beispielsweise kann "file" im Hauptmenü der Anwendung anders als die Zeichenfolge "file" in einem Dialogfeld übersetzt werden. Wenn Sie mehr als eine Zeichenfolge mit demselben Namen verwenden müssen, verwenden Sie jeweils unterschiedliche Zeichen folgen-IDs.

- Möglicherweise möchten Sie herausfinden, ob Ihre Anwendung auf einem MBCS-fähigen Betriebssystem ausgeführt wird. Legen Sie zu diesem Zweck ein Flag beim Programmstart fest. verlassen Sie sich nicht auf API-Aufrufe.

- Wenn Sie Dialogfelder entwerfen, sollten Sie am Ende der statischen Text Steuerelemente für die MBCS-Übersetzung ca. 30% zusätzlichen Bereich zulassen.

- Gehen Sie bei der Auswahl von Schriftarten für Ihre Anwendung vorsichtig vor, da einige Schriftarten nicht auf allen Systemen verfügbar sind.

- Wenn Sie die Schriftart für Dialogfelder auswählen, verwenden Sie [MS Shell Dlg](/windows/win32/Intl/using-ms-shell-dlg-and-ms-shell-dlg-2) anstelle von MS Sans Serif oder Helvetica. MS Shell Dlg wird durch das System vor dem Erstellen des Dialog Felds durch die richtige Schriftart ersetzt. Durch die Verwendung von MS Shell Dlg wird sichergestellt, dass alle Änderungen im Betriebssystem, die mit dieser Schriftart zu tun haben, automatisch verfügbar sind. (MFC ersetzt MS Shell Dlg durch die DEFAULT_GUI_FONT oder die System Schriftart unter Windows 95, Windows 98 und Windows NT 4, weil diese Systeme MS Shell Dlg nicht ordnungsgemäß verarbeiten.)

- Wenn Sie Ihre Anwendung entwerfen, entscheiden Sie, welche Zeichen folgen lokalisiert werden können. Nehmen Sie im Zweifelsfall an, dass eine angegebene Zeichenfolge lokalisiert wird. Kombinieren Sie daher keine Zeichen folgen, die mit denen, die nicht möglich sind, lokalisiert werden können.

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)
