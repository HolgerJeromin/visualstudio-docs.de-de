---
title: Festlegen des Steuerelements, das beim Ziehen aus dem Datenquellenfenster erstellt werden soll
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Data Sources Window, select controls
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- data [Visual Studio], Data Sources window
ms.assetid: 20597ff8-0c98-43ec-8fb1-05376804ba48
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a72800cda8b80daec1adeb82d7884789cc4d2bd7
ms.sourcegitcommit: f37affbc1b885dfe246d4b2c295a6538b383a0ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37174165"
---
# <a name="set-the-control-to-be-created-when-dragging-from-the-data-sources-window"></a>Festlegen des Steuerelements, das beim Ziehen aus dem Datenquellenfenster erstellt werden soll
Sie können datengebundene Steuerelemente durch Ziehen von Elementen aus der **Datenquellen** Fenster in den WPF- oder Windows Forms-Designer. Jedes Element in der **Datenquellen** verfügt über ein Standardsteuerelement, das erstellt wird, wenn Sie es in den Designer ziehen. Sie können jedoch ein anderes Steuerelement erstellen.

## <a name="set-the-controls-to-be-created-for-data-tables-or-objects"></a>Festlegen der Kontrollen, die für Datentabellen oder Objekte erstellt werden
Bevor Sie Elemente ziehen, die die Datentabellen oder Objekte darstellen der **Datenquellen** Fenster können Sie auswählen, um alle Daten in einem Steuerelement angezeigt werden, oder jede Spalte oder Eigenschaft in einem separaten Steuerelement angezeigt.

In diesem Kontext ist der Begriff *Objekt* bezieht sich auf ein benutzerdefiniertes Geschäftsobjekt, eine Entität (in einem Entity Data Model) oder ein Objekt, das von einem Dienst zurückgegeben.

### <a name="to-set-the-controls-to-be-created-for-data-tables-or-objects"></a>So legen Sie die Steuerelemente fest, die für Datentabellen oder Objekte erstellt werden sollen

1.  Achten Sie darauf die **WPF** Designer oder dem **Windows Forms** -Designer geöffnet ist.

2.  In der **Datenquellen** Fenster, wählen Sie das Element, die die Datentabelle darstellt, oder ein Objekt festgelegt werden soll.

3.  Klicken Sie auf das Dropdownmenü für das Element, und klicken Sie im Menü auf eines der folgenden Elemente:

    -   Um jedes Datenfeld in einem separaten Steuerelement anzuzeigen, klicken Sie auf **Details**. Wenn Sie das Datenelement in den Designer ziehen, werden für jede Spalte bzw. jede Eigenschaft der übergeordneten Datentabelle oder des Objekts ein anderes datengebundenes Steuerelement sowie Bezeichnungen für jedes Steuerelement erstellt.

    -   Um alle Daten in einem einzelnen Steuerelement anzuzeigen, wählen Sie ein anderes Steuerelement in der Liste, z. B. **DataGrid** oder **Liste** in einer WPF-Anwendung oder **DataGridView** in einem Windows Forms die Anwendung.

    Die Liste der verfügbaren Steuerelemente hängt Designer Sie geöffnet, welche Version von .NET Framework das Projekt abzielt haben, und gibt an, ob Sie benutzerdefinierte Steuerelemente hinzugefügt haben, Unterstützung der Datenbindung an die **Toolbox**. Wenn das Steuerelement, die, das Sie erstellen möchten, nicht in der Liste der verfügbaren Steuerelemente ist, können Sie das Steuerelement zur Liste hinzufügen. Weitere Informationen finden Sie unter [Hinzufügen benutzerdefinierter Steuerelemente zum Datenquellenfenster](../data-tools/add-custom-controls-to-the-data-sources-window.md).

    Erfahren Sie, wie ein benutzerdefiniertes Windows Forms-Steuerelement zu erstellen, die die Liste der Steuerelemente für Datentabellen oder Objekte im hinzugefügt werden, können, die **Datenquellen** Fenster finden Sie unter [Erstellen eines Windows Forms-Benutzersteuerelements, die komplexe Daten unterstützt Binden von](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).

## <a name="set-the-controls-to-be-created-for-data-columns-or-properties"></a>Legen Sie die Steuerelemente für Datenspalten oder-Eigenschaften erstellt werden soll
Bevor Sie ein Element, das eine Spalte oder eine Eigenschaft eines Objekts aus darstellt, ziehen die **Datenquellen** Fenster in den Designer können Sie die zu erstellende Steuerelement festlegen.

#### <a name="to-set-the-controls-to-be-created-for-columns-or-properties"></a>So legen Sie die Steuerelemente fest, die für Spalten oder Eigenschaften erstellt werden sollen

1.  Achten Sie darauf die **WPF** Designer oder dem **Windows Forms** -Designer geöffnet ist.

2.  In der **Datenquellen** Fenster, erweitern Sie die gewünschte Tabelle oder das Objekt, für die Spalten bzw. Eigenschaften angezeigt.

3.  Wählen Sie jede Spalte oder jede Eigenschaft aus, für die das Steuerelement erstellt werden soll.

4.  Klicken Sie auf das Dropdownmenü für die Spalte oder die Eigenschaft, und wählen Sie das Steuerelement aus, das beim Ziehen des Elements in den Designer erstellt werden soll.

     Die Liste der verfügbaren Steuerelemente hängt Designer Sie geöffnet, welche Version von .NET Framework das Projekt abzielt haben, und welche benutzerdefinierten Steuerelemente, unterstützen, die Daten, die Bindung, die Sie hinzugefügt haben die **Toolbox**. Wenn das gewünschte Steuerelement in der Liste der verfügbaren Steuerelemente aufgeführt ist, können Sie der Liste das Steuerelement hinzufügen. Weitere Informationen finden Sie unter [Hinzufügen benutzerdefinierter Steuerelemente zum Datenquellenfenster](../data-tools/add-custom-controls-to-the-data-sources-window.md).

     Erfahren Sie, wie ein benutzerdefiniertes Steuerelement erstellen, die die Liste der Steuerelemente für Datenspalten oder Eigenschaften im hinzugefügt werden, können, die **Datenquellen** Fenster finden Sie unter [Erstellen eines Windows Forms-Benutzersteuerelements, die einfache Datenbindungunterstützt](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).

     Wenn Sie ein Steuerelement für die Spalte oder Eigenschaft erstellen möchten, wählen Sie **keine** im Dropdown-Menü. Dies ist nützlich, wenn Sie die übergeordnete Tabelle oder das Objekt in den Designer ziehen, aber die Spalte oder die Eigenschaft nicht einschließen möchten.

## <a name="see-also"></a>Siehe auch

- [Binden von Steuerelementen an Daten in Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)