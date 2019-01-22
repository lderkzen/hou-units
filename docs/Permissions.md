# Permissions
Permissions are validated via policies. There's no validation against direct roles or claims.  
A user must fulfill a policy in order to access or use a certain view or function.

## Public Actions
These actions are available to everyone, without any authentication or policy:
- Login
- Read privacy statement
- Read imprint

## Guild Member Actions
These actions require a login, and therefore are only available to guild members.  
`Any Guild Member` that is allowed to use the system, **except** when they have been **blocked** from the system explicitly.  
Guild members can perform ***basic actions***, as well as ***advanced actions***, whereas the later require the fulfillment of certain policies, listed below.

### Basic Actions
- Open settings
- Open profile
- Logout
- Change the displayed times / time zone
- See the current token balance
- See the token forecast
- See the token history
- See future events
- See trading offers
- See trading requests
- See guild bank store
- See guild bank donations
- See service requests

### Advanced Actions

#### Event Related Policies
| Policy Name | Condition |
| --- | --- |
| CreateEvent | Must be a `Leader`, `Officer`, or `Coordinator`. |
| EditEvent | Must be a `Leader`, `Officer`, or `Coordinator`, and either the event creator, or a higher rank than the person who created the event. |
| CancelEvent | Must be a `Leader`, `Officer`, or `Coordinator`, and either the event creator, or a higher rank than the person who created the event. |
| CreateEventSeries | Must be a `Leader` or `Officer`. |
| EditEventSeries | Must be a `Leader`,<br>- or -<br>Must be an `Officer` and the creator of the event. |
| CancelEventSeries | Must be a `Leader`,<br>- or -<br>Must be an `Officer` and the creator of the event. |
| JoinEvent | Must be `Any Guild Member`, but not blacklisted from joining events. |
| LeaveEvent | Must be `Any Guild Member`, but not the creator of the event. |
| CheckEventAttendance | Must be a `Leader`, `Officer`, or `Coordinator`, who created or joined the event. |
| AddToJoinEventsBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromJoinEventsBlacklist | Must be a `Leader` or `Officer`. |
| SeePastEvents | Must be a `Leader` or `Officer`,<br>- or -<br>Must be `Any Guild Member`, who created or joined the event. |

---

#### Service Related Policies
| Policy Name | Condition |
| --- | --- |
| CreateServiceRequest | Must be `Any Guild Member`, but not blacklisted from creating service requests. |
| CancelServiceRequest | Must be `Any Guild Member`, and the creator of the service request. |
| ReplyServiceRequest | Must be `Any Guild Member`, but not blacklisted from replying service requests. |
| ConfirmServiceRequest | Must be `Any Guild Member`, and either the creator of the service request or person replying to the service request. |
| ReportServiceIssue | Must be `Any Guild Member`, and either the creator of the service request or person replying to the service request. |
| AddToCreateServiceRequestBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromCreateServiceRequestBlacklist | Must be a `Leader` or `Officer`. |
| AddToReplyServiceRequestBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromReplyServiceRequestBlacklist | Must be a `Leader` or `Officer`. |
| SeePastServiceRequests | Must be a `Leader` or `Officer`,<br>- or -<br>Must be `Any Guild Member`, who created the service request or replied to the service request. |
| RevertCompletedServiceRequest | Must be a `Leader`. |

---

#### Trading Related Policies
| Policy Name | Condition |
| --- | --- |
| CreateTradeOffer | Must be `Any Guild Member`, but not blacklisted from creating trade offers. |
| CancelTradeOffer | Must be `Any Guild Member`, and the creator of the trade offer. |
| CreateTradeRequest | Must be `Any Guild Member`, but not blacklisted from creating trade requests. |
| CancelTradeRequest | Must be `Any Guild Member`, and the creator of the trade request. |
| ReplyTradeOffer | Must be `Any Guild Member`, but not blacklisted from replying trade offers. |
| ReplyTradeRequest | Must be `Any Guild Member`, but not blacklisted from replying trade requests. |
| ConfirmTrade | Must be `Any Guild Member`, and either the creator of the trade or person replying to the trade. |
| ReportTradeIssue | Must be `Any Guild Member`, and either the creator of the trade or person replying to the trade. |
| AddToCreateTradeOfferBlacklist | Must be a `Leader` or `Officer`. |
| RemoveCreateTradeOfferBlacklist | Must be a `Leader` or `Officer`. |
| AddToCreateTradeRequestBlacklist | Must be a `Leader` or `Officer`. |
| RemoveCreateTradeRequestBlacklist | Must be a `Leader` or `Officer`. |
| AddToReplyTradeOfferBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromReplyTradeOfferBlacklist | Must be a `Leader` or `Officer`. |
| AddToReplyTradeRequestBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromReplyTradeRequestBlacklist | Must be a `Leader` or `Officer`. |
| SeePastTrades | Must be a `Leader` or `Officer`,<br>- or -<br>Must be `Any Guild Member`, who created the trade or participated in the trade. |
| SeeOngoingTrades | Must be a `Leader` or `Officer`. |
| RevertCompletedTrade | Must be a `Leader`. |

---

#### Guild Bank Related Policies
| Policy Name | Condition |
| --- | --- |
| CreateDonationRequest | Must be a `Leader` or `Quartermaster`. |
| CancelDonationRequest | Must be a `Leader` or `Quartermaster`. |
| CreatePurchasableGuildBankItem | Must be a `Leader` or `Officer`. |
| CancelPurchasableGuildBankItem | Must be a `Leader` or `Officer`. |
| ReplyDonationRequest | Must be `Any Guild Member`, but not blacklisted from replying donation requests. |
| ReplyPurchasableGuildBankItem | Must be `Any Guild Member`, but not blacklisted from replying purchasable guild bank items. |
| AcceptGuildBankTrade | Must be a `Leader` or `Officer`. |
| ConfirmGuildBankTrade | Must be a `Leader` or `Officer`, and the person who accepted the guild bank trade,<br>- or -<br>Must be `Any Guild Member`, and the person replying to the guild bank trade. |
| AddToReplyDonationRequestBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromReplyDonationRequestBlacklist | Must be a `Leader` or `Officer`. |
| AddToReplyPurchasableGuildBankItemBlacklist | Must be a `Leader` or `Officer`. |
| RemoveFromReplyPurchasableGuildBankItemBlacklist | Must be a `Leader` or `Officer`. |
| SeePastGuildBankPurchases | Must be a `Any Guild Member`. |
| SeePastGuildBankDonations | Must be a `Leader` or `Officer`. |
| SeeOngoingGuildBankTrades | Must be a `Leader` or `Officer`. |
| RevertCompletedGuildBankDonation | Must be a `Leader` or `Quartermaster`. |
| RevertCompletedGuildBankPurchase | Must be a `Leader` or `Quartermaster`. |

---

#### Profile Related Policies
| Policy Name | Condition |
| --- | --- |
| ObtainTitle | Must be `Any Guild Member`, who reached 500 tokens at least once. |

---

#### Additional Administration Policies
| Policy Name | Condition |
| --- | --- |
| ManageItems | Must be a `Leader` or `Officer`. |
| DenyLoginForGuildMember | Must be a `Leader` or `Officer`. |
| GrantLoginForGuildMember | Must be a `Leader` or `Officer`. |
| ManageSystemSettings | Must be a `Leader` or `Developer`. |