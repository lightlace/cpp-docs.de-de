---
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: a5f60e1ba8c2b68ddca312859694f532e38da965
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365157"
---
# <a name="mapi"></a>MAPI

Dieser Artikel beschreibt die Microsoft MAPI Messaging Application Programming Interface () für den Entwicklern von Clientanwendungen die Nachricht an. MFC bietet Unterstützung für eine Teilmenge von MAPI in Klasse `CDocument` jedoch nicht die gesamte API gekapselt ist. Weitere Informationen finden Sie unter [MAPI-Unterstützung in MFC](../mfc/mapi-support-in-mfc.md).

MAPI ist ein Satz von Funktionen, die e-Mail-aktivierte und e-Mail-fähige Anwendungen, die zum Erstellen, bearbeiten, übertragen und speichern die e-Mail-Nachrichten verwenden. Es bietet Entwicklern die Tools, um den Zweck und den Inhalt der e-Mail-Nachrichten zu definieren und erhalten sie Flexibilität in der ihre Verwaltung gespeicherter e-Mail-Nachrichten. MAPI bietet auch eine gemeinsame Schnittstelle, die Entwickler von Anwendungen verwenden können, um e-Mail-aktivierte zu erstellen und e-Mail-fähigen Anwendungen, die unabhängig von der zugrunde liegenden messaging-System.

Messaging-Clients bieten eine interaktive Oberfläche für die Interaktion mit dem Microsoft Windows Messaging System (WMS). Diese Interaktion umfasst in der Regel, die von MAPI-kompatibles Anbietern wie Nachrichtenspeichern und Adressbücher Dienste anfordern.

Weitere Informationen zu MAPI finden Sie unter den Artikeln der Anleitung in Win32 MAPI (Messaging) des Windows SDK.

## <a name="in-this-section"></a>In diesem Abschnitt

[MAPI-Unterstützung in MFC](../mfc/mapi-support-in-mfc.md)

## <a name="see-also"></a>Siehe auch

[CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)
