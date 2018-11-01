---
title: Allgemeine Ratschläge für die MBCS-Programmierung
ms.date: 11/04/2016
f1_keywords:
- _mbcs
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
ms.openlocfilehash: 0ff15244f4e93ecd2913fa825e8b5c351c7ff84d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501841"
---
# <a name="general-mbcs-programming-advice"></a>Allgemeine Ratschläge für die MBCS-Programmierung

Verwenden Sie die folgenden Tipps:

- Verwenden Sie für mehr Flexibilität Laufzeit-Makros wie `_tcschr` und `_tcscpy` Wenn möglich. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).

- Verwenden Sie die C-Laufzeit `_getmbcp` Funktion zum Abrufen von Informationen über die aktuelle Codepage.

- Zeichenfolgenressourcen nicht wiederverwendet werden. Abhängig von der Zielsprache möglicherweise eine angegebene Zeichenfolge eine unterschiedliche Bedeutung, wenn übersetzt. Hauptmenü "Datei" in der Anwendung könnte z. B. unterschiedlich aus der Zeichenfolge "File" in einem Dialogfeld übersetzen. Wenn Sie mehr als eine Zeichenfolge mit dem gleichen Namen verwenden müssen, verwenden Sie für jeden anderen Zeichenfolgen-IDs.

- Sie möchten herausfinden, ob Ihre Anwendung auf einem MBCS-fähigen Betriebssystem ausgeführt wird. Zu diesem Zweck legen Sie ein Flag beim Programmstart; verlassen Sie sich nicht auf die API-Aufrufe.

- Beim Entwurf von Dialogfeldern können Sie etwa 30 Prozent zusätzliche Leerzeichen am Ende von statischen Steuerelementen für die MBCS-Übersetzung.

- Achten Sie darauf beim Auswählen von Schriftarten für Ihre Anwendung, da es sich bei einigen Schriftarten nicht auf allen Systemen verfügbar sind.

- Verwenden Sie bei der Auswahl der Schriftart für Dialogfelder [MS Shell Dlg](/windows/desktop/Intl/using-ms-shell-dlg-and-ms-shell-dlg-2) anstelle von MS Sans Serif oder Helvetica. MS Shell Dlg wird durch die richtige Schriftart vom System ersetzt, vor dem Erstellen des Dialogfelds. Mithilfe von MS Shell Dlg wird sichergestellt, dass alle Änderungen an der das Betriebssystem für den Umgang mit dieser Schriftart automatisch zur Verfügung stehen. (MFC haben MS Shell Dlg DEFAULT_GUI_FONT oder Systemschriftart auf Windows 95, Windows 98 und Windows NT 4 ersetzt, da diese Systeme MS Shell Dlg nicht ordnungsgemäß behandelt werden.)

- Beim Entwerfen Ihrer Anwendung entscheiden Sie, welche Zeichenfolgen lokalisiert werden können. Im Zweifelsfall wird davon ausgegangen Sie, dass jedes lokalisiert wird. Kombinieren Sie Zeichenfolgen, die lokalisiert werden können, nicht mit denjenigen, die nicht.

## <a name="see-also"></a>Siehe auch

[Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)<br/>
[Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)