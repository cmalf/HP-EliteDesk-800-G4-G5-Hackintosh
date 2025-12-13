# ACPI Patches Changelog

| Based OC  | Path      | Changes                                                                                                                                                                    |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1.0.6** | `OC/ACPI` | **SSDT-PTS** <br> <sub>Bug fix regarding serialization status.</sub> <br> 🔴 **Remove:** `Method (_PTS, 1, Serialized)` <br> 🟢 **Add:** `Method (_PTS, 1, NotSerialized)` |
