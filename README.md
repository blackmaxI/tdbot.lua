# tdbot.lua
A simple Lua wrapper for [`telegram-bot`](https://valtman.name/telegram-bot).

See [wiki](https://github.com/rizaumami/tdbot.lua/wiki) for documentation.

## How to Use

- Put `tdbot.lua` on a same directory level with your bot script
- Import `tdbot.lua` into your bot.
- Call the functions.

See example script below.

```lua
-- Load tdbot library.
tdbot = require 'tdbot'

-- An alias to sendText
function sendText(chat_id, reply_to_message_id, text)
  tdbot.sendText(chat_id, reply_to_message_id, text, 0, 1, nil, 1, 'html', 0, nil)
end

function tdbot_update_callback (data)
  if (data._ == "updateNewMessage") then
    local msg = data.message

    if msg.content._ == "messageText" then
      if msg.content.text == "ping" then
          sendText(chat_id, msg.id, '<b>pong!</b>')
        }, dl_cb, nil))
      end
    end
  end
end

```

## The Functions

`tdbot.lua` is a _Work In Progress_. This commit is based on [telegram-bot-171006-nightly.tl](https://valtman.name/files/telegram-bot-171006-nightly.tl) scheme.  
Here is a list of `telegram-bot` methods. Checked functions has been tested and works or returned "ok".

- [x] [getAuthState](https://github.com/rizaumami/tdbot.lua/wiki/getAuthState)
- [ ] [setAuthPhoneNumber](https://github.com/rizaumami/tdbot.lua/wiki/setAuthPhoneNumber)
- [x] [resendAuthCode](https://github.com/rizaumami/tdbot.lua/wiki/resendAuthCode)
- [ ] [checkAuthCode](https://github.com/rizaumami/tdbot.lua/wiki/checkAuthCode)
- [ ] [checkAuthPassword](https://github.com/rizaumami/tdbot.lua/wiki/checkAuthPassword)
- [ ] [requestAuthPasswordRecovery](https://github.com/rizaumami/tdbot.lua/wiki/requestAuthPasswordRecovery)
- [ ] [recoverAuthPassword](https://github.com/rizaumami/tdbot.lua/wiki/recoverAuthPassword)
- [x] [resetAuth](https://github.com/rizaumami/tdbot.lua/wiki/resetAuth)
- [x] [checkAuthBotToken](https://github.com/rizaumami/tdbot.lua/wiki/checkAuthBotToken)
- [x] [getPasswordState](https://github.com/rizaumami/tdbot.lua/wiki/getPasswordState)
- [x] [setPassword](https://github.com/rizaumami/tdbot.lua/wiki/setPassword)
- [x] [getRecoveryEmail](https://github.com/rizaumami/tdbot.lua/wiki/getRecoveryEmail)
- [x] [setRecoveryEmail](https://github.com/rizaumami/tdbot.lua/wiki/setRecoveryEmail)
- [x] [requestPasswordRecovery](https://github.com/rizaumami/tdbot.lua/wiki/requestPasswordRecovery)
- [x] [recoverPassword](https://github.com/rizaumami/tdbot.lua/wiki/recoverPassword)
- [x] [createTemporaryPassword](https://github.com/rizaumami/tdbot.lua/wiki/createTemporaryPassword)
- [x] [getTemporaryPasswordState](https://github.com/rizaumami/tdbot.lua/wiki/getTemporaryPasswordState)
- [ ] [processDcUpdate](https://github.com/rizaumami/tdbot.lua/wiki/processDcUpdate)
- [x] [getMe](https://github.com/rizaumami/tdbot.lua/wiki/getMe)
- [x] [getUser](https://github.com/rizaumami/tdbot.lua/wiki/getUser)
- [x] [getUserFull](https://github.com/rizaumami/tdbot.lua/wiki/getUserFull)
- [x] [getGroup](https://github.com/rizaumami/tdbot.lua/wiki/getGroup)
- [x] [getGroupFull](https://github.com/rizaumami/tdbot.lua/wiki/getGroupFull)
- [x] [getChannel](https://github.com/rizaumami/tdbot.lua/wiki/getChannel)
- [x] [getChannelFull](https://github.com/rizaumami/tdbot.lua/wiki/getChannelFull)
- [x] [getSecretChat](https://github.com/rizaumami/tdbot.lua/wiki/getSecretChat)
- [x] [getChat](https://github.com/rizaumami/tdbot.lua/wiki/getChat)
- [x] [getMessage](https://github.com/rizaumami/tdbot.lua/wiki/getMessage)
- [x] [getMessages](https://github.com/rizaumami/tdbot.lua/wiki/getMessages)
- [x] [getFile](https://github.com/rizaumami/tdbot.lua/wiki/getFile)
- [x] [getFilePersistent](https://github.com/rizaumami/tdbot.lua/wiki/getFilePersistent)
- [x] [getChats](https://github.com/rizaumami/tdbot.lua/wiki/getChats)
- [x] [searchPublicChat](https://github.com/rizaumami/tdbot.lua/wiki/searchPublicChat)
- [x] [searchPublicChats](https://github.com/rizaumami/tdbot.lua/wiki/searchPublicChats)
- [x] [searchChats](https://github.com/rizaumami/tdbot.lua/wiki/searchChats)
- [x] [getTopChats](https://github.com/rizaumami/tdbot.lua/wiki/getTopChats)
- [x] [deleteTopChat](https://github.com/rizaumami/tdbot.lua/wiki/deleteTopChat)
- [x] [addRecentlyFoundChat](https://github.com/rizaumami/tdbot.lua/wiki/addRecentlyFoundChat)
- [x] [deleteRecentlyFoundChat](https://github.com/rizaumami/tdbot.lua/wiki/deleteRecentlyFoundChat)
- [x] [deleteRecentlyFoundChats](https://github.com/rizaumami/tdbot.lua/wiki/deleteRecentlyFoundChats)
- [x] [getCommonChats](https://github.com/rizaumami/tdbot.lua/wiki/getCommonChats)
- [x] [getCreatedPublicChats](https://github.com/rizaumami/tdbot.lua/wiki/getCreatedPublicChats)
- [x] [getChatHistory](https://github.com/rizaumami/tdbot.lua/wiki/getChatHistory)
- [x] [deleteChatHistory](https://github.com/rizaumami/tdbot.lua/wiki/deleteChatHistory)
- [x] [searchChatMessages](https://github.com/rizaumami/tdbot.lua/wiki/searchChatMessages)
- [x] [searchMessages](https://github.com/rizaumami/tdbot.lua/wiki/searchMessages)
- [x] [searchSecretMessages](https://github.com/rizaumami/tdbot.lua/wiki/searchSecretMessages)
- [x] [searchCallMessages](https://github.com/rizaumami/tdbot.lua/wiki/searchCallMessages)
- [x] [getPublicMessageLink](https://github.com/rizaumami/tdbot.lua/wiki/getPublicMessageLink)
- [x] [sendMessage](https://github.com/rizaumami/tdbot.lua/wiki/sendMessage)
- [x] [sendBotStartMessage](https://github.com/rizaumami/tdbot.lua/wiki/sendBotStartMessage)
- [ ] [sendInlineQueryResultMessage](https://github.com/rizaumami/tdbot.lua/wiki/sendInlineQueryResultMessage)
- [x] [forwardMessages](https://github.com/rizaumami/tdbot.lua/wiki/forwardMessages)
- [x] [sendChatSetTtlMessage](https://github.com/rizaumami/tdbot.lua/wiki/sendChatSetTtlMessage)
- [x] [sendChatScreenshotTakenNotification](https://github.com/rizaumami/tdbot.lua/wiki/sendChatScreenshotTakenNotification)
- [x] [deleteMessages](https://github.com/rizaumami/tdbot.lua/wiki/deleteMessages)
- [x] [deleteMessagesFromUser](https://github.com/rizaumami/tdbot.lua/wiki/deleteMessagesFromUser)
- [x] [editMessageText](https://github.com/rizaumami/tdbot.lua/wiki/editMessageText)
- [x] [editMessageCaption](https://github.com/rizaumami/tdbot.lua/wiki/editMessageCaption)
- [ ] [editMessageReplyMarkup](https://github.com/rizaumami/tdbot.lua/wiki/editMessageReplyMarkup)
- [ ] [editInlineMessageText](https://github.com/rizaumami/tdbot.lua/wiki/editInlineMessageText)
- [ ] [editInlineMessageCaption](https://github.com/rizaumami/tdbot.lua/wiki/editInlineMessageCaption)
- [ ] [editInlineMessageReplyMarkup](https://github.com/rizaumami/tdbot.lua/wiki/editInlineMessageReplyMarkup)
- [x] [getTextEntities](https://github.com/rizaumami/tdbot.lua/wiki/getTextEntities)
- [x] [getFileMimeType](https://github.com/rizaumami/tdbot.lua/wiki/getFileMimeType)
- [x] [getFileExtension](https://github.com/rizaumami/tdbot.lua/wiki/getFileExtension)
- [x] [getInlineQueryResults](https://github.com/rizaumami/tdbot.lua/wiki/getInlineQueryResults)
- [ ] [answerInlineQuery](https://github.com/rizaumami/tdbot.lua/wiki/answerInlineQuery)
- [ ] [getCallbackQueryAnswer](https://github.com/rizaumami/tdbot.lua/wiki/getCallbackQueryAnswer)
- [ ] [answerCallbackQuery](https://github.com/rizaumami/tdbot.lua/wiki/answerCallbackQuery)
- [ ] [answerShippingQuery](https://github.com/rizaumami/tdbot.lua/wiki/answerShippingQuery)
- [ ] [answerPreCheckoutQuery](https://github.com/rizaumami/tdbot.lua/wiki/answerPreCheckoutQuery)
- [ ] [setGameScore](https://github.com/rizaumami/tdbot.lua/wiki/setGameScore)
- [ ] [setInlineGameScore](https://github.com/rizaumami/tdbot.lua/wiki/setInlineGameScore)
- [ ] [getGameHighScores](https://github.com/rizaumami/tdbot.lua/wiki/getGameHighScores)
- [ ] [getInlineGameHighScores](https://github.com/rizaumami/tdbot.lua/wiki/getInlineGameHighScores)
- [ ] [deleteChatReplyMarkup](https://github.com/rizaumami/tdbot.lua/wiki/deleteChatReplyMarkup)
- [x] [sendChatAction](https://github.com/rizaumami/tdbot.lua/wiki/sendChatAction)
- [x] [openChat](https://github.com/rizaumami/tdbot.lua/wiki/openChat)
- [x] [closeChat](https://github.com/rizaumami/tdbot.lua/wiki/closeChat)
- [x] [viewMessages](https://github.com/rizaumami/tdbot.lua/wiki/viewMessages)
- [x] [openMessageContent](https://github.com/rizaumami/tdbot.lua/wiki/openMessageContent)
- [x] [createPrivateChat](https://github.com/rizaumami/tdbot.lua/wiki/createPrivateChat)
- [x] [createGroupChat](https://github.com/rizaumami/tdbot.lua/wiki/createGroupChat)
- [x] [createChannelChat](https://github.com/rizaumami/tdbot.lua/wiki/createChannelChat)
- [x] [createSecretChat](https://github.com/rizaumami/tdbot.lua/wiki/createSecretChat)
- [x] [createNewGroupChat](https://github.com/rizaumami/tdbot.lua/wiki/createNewGroupChat)
- [x] [createNewChannelChat](https://github.com/rizaumami/tdbot.lua/wiki/createNewChannelChat)
- [x] [createNewSecretChat](https://github.com/rizaumami/tdbot.lua/wiki/createNewSecretChat)
- [x] [migrateGroupChatToChannelChat](https://github.com/rizaumami/tdbot.lua/wiki/migrateGroupChatToChannelChat)
- [x] [changeChatTitle](https://github.com/rizaumami/tdbot.lua/wiki/changeChatTitle)
- [x] [changeChatPhoto](https://github.com/rizaumami/tdbot.lua/wiki/changeChatPhoto)
- [x] [changeChatDraftMessage](https://github.com/rizaumami/tdbot.lua/wiki/changeChatDraftMessage)
- [x] [toggleChatIsPinned](https://github.com/rizaumami/tdbot.lua/wiki/toggleChatIsPinned)
- [ ] [setChatClientData](https://github.com/rizaumami/tdbot.lua/wiki/setChatClientData)
- [x] [addChatMember](https://github.com/rizaumami/tdbot.lua/wiki/addChatMember)
- [x] [addChatMembers](https://github.com/rizaumami/tdbot.lua/wiki/addChatMembers)
- [x] [changeChatMemberStatus](https://github.com/rizaumami/tdbot.lua/wiki/changeChatMemberStatus)
- [x] [getChatMember](https://github.com/rizaumami/tdbot.lua/wiki/getChatMember)
- [x] [searchChatMembers](https://github.com/rizaumami/tdbot.lua/wiki/searchChatMembers)
- [x] [setPinnedChats](https://github.com/rizaumami/tdbot.lua/wiki/setPinnedChats)
- [x] [downloadFile](https://github.com/rizaumami/tdbot.lua/wiki/downloadFile)
- [x] [cancelDownloadFile](https://github.com/rizaumami/tdbot.lua/wiki/cancelDownloadFile)
- [ ] [uploadFile](https://github.com/rizaumami/tdbot.lua/wiki/uploadFile)
- [ ] [cancelUploadFile](https://github.com/rizaumami/tdbot.lua/wiki/cancelUploadFile)
- [ ] [setFileGenerationProgress](https://github.com/rizaumami/tdbot.lua/wiki/setFileGenerationProgress)
- [ ] [finishFileGeneration](https://github.com/rizaumami/tdbot.lua/wiki/finishFileGeneration)
- [x] [deleteFile](https://github.com/rizaumami/tdbot.lua/wiki/deleteFile)
- [x] [exportChatInviteLink](https://github.com/rizaumami/tdbot.lua/wiki/exportChatInviteLink)
- [x] [checkChatInviteLink](https://github.com/rizaumami/tdbot.lua/wiki/checkChatInviteLink)
- [x] [importChatInviteLink](https://github.com/rizaumami/tdbot.lua/wiki/importChatInviteLink)
- [ ] [createCall](https://github.com/rizaumami/tdbot.lua/wiki/createCall)
- [ ] [acceptCall](https://github.com/rizaumami/tdbot.lua/wiki/acceptCall)
- [ ] [discardCall](https://github.com/rizaumami/tdbot.lua/wiki/discardCall)
- [ ] [rateCall](https://github.com/rizaumami/tdbot.lua/wiki/rateCall)
- [ ] [debugCall](https://github.com/rizaumami/tdbot.lua/wiki/debugCall)
- [x] [blockUser](https://github.com/rizaumami/tdbot.lua/wiki/blockUser)
- [x] [unblockUser](https://github.com/rizaumami/tdbot.lua/wiki/unblockUser)
- [x] [getBlockedUsers](https://github.com/rizaumami/tdbot.lua/wiki/getBlockedUsers)
- [x] [importContacts](https://github.com/rizaumami/tdbot.lua/wiki/importContacts)
- [x] [searchContacts](https://github.com/rizaumami/tdbot.lua/wiki/searchContacts)
- [x] [deleteContacts](https://github.com/rizaumami/tdbot.lua/wiki/deleteContacts)
- [ ] [getImportedContactCount](https://github.com/rizaumami/tdbot.lua/wiki/getImportedContactCount)
- [ ] [deleteImportedContacts](https://github.com/rizaumami/tdbot.lua/wiki/deleteImportedContacts)
- [x] [getUserProfilePhotos](https://github.com/rizaumami/tdbot.lua/wiki/getUserProfilePhotos)
- [x] [getStickers](https://github.com/rizaumami/tdbot.lua/wiki/getStickers)
- [x] [getInstalledStickerSets](https://github.com/rizaumami/tdbot.lua/wiki/getInstalledStickerSets)
- [x] [getArchivedStickerSets](https://github.com/rizaumami/tdbot.lua/wiki/getArchivedStickerSets)
- [x] [getTrendingStickerSets](https://github.com/rizaumami/tdbot.lua/wiki/getTrendingStickerSets)
- [ ] [getAttachedStickerSets](https://github.com/rizaumami/tdbot.lua/wiki/getAttachedStickerSets)
- [x] [getStickerSet](https://github.com/rizaumami/tdbot.lua/wiki/getStickerSet)
- [x] [searchStickerSet](https://github.com/rizaumami/tdbot.lua/wiki/searchStickerSet)
- [x] [changeStickerSet](https://github.com/rizaumami/tdbot.lua/wiki/changeStickerSet)
- [ ] [viewTrendingStickerSets](https://github.com/rizaumami/tdbot.lua/wiki/viewTrendingStickerSets)
- [ ] [reorderInstalledStickerSets](https://github.com/rizaumami/tdbot.lua/wiki/reorderInstalledStickerSets)
- [x] [getRecentStickers](https://github.com/rizaumami/tdbot.lua/wiki/getRecentStickers)
- [x] [addRecentSticker](https://github.com/rizaumami/tdbot.lua/wiki/addRecentSticker)
- [x] [deleteRecentSticker](https://github.com/rizaumami/tdbot.lua/wiki/deleteRecentSticker)
- [x] [clearRecentStickers](https://github.com/rizaumami/tdbot.lua/wiki/clearRecentStickers)
- [x] [getFavoriteStickers](https://github.com/rizaumami/tdbot.lua/wiki/getFavoriteStickers)
- [x] [addFavoriteSticker](https://github.com/rizaumami/tdbot.lua/wiki/addFavoriteSticker)
- [x] [deleteFavoriteSticker](https://github.com/rizaumami/tdbot.lua/wiki/deleteFavoriteSticker)
- [x] [getStickerEmojis](https://github.com/rizaumami/tdbot.lua/wiki/getStickerEmojis)
- [x] [getSavedAnimations](https://github.com/rizaumami/tdbot.lua/wiki/getSavedAnimations)
- [x] [addSavedAnimation](https://github.com/rizaumami/tdbot.lua/wiki/addSavedAnimation)
- [x] [deleteSavedAnimation](https://github.com/rizaumami/tdbot.lua/wiki/deleteSavedAnimation)
- [x] [getRecentInlineBots](https://github.com/rizaumami/tdbot.lua/wiki/getRecentInlineBots)
- [x] [searchHashtags](https://github.com/rizaumami/tdbot.lua/wiki/searchHashtags)
- [x] [deleteRecentHashtag](https://github.com/rizaumami/tdbot.lua/wiki/deleteRecentHashtag)
- [x] [getWebPagePreview](https://github.com/rizaumami/tdbot.lua/wiki/getWebPagePreview)
- [x] [getWebPageInstantView](https://github.com/rizaumami/tdbot.lua/wiki/getWebPageInstantView)
- [x] [getNotificationSettings](https://github.com/rizaumami/tdbot.lua/wiki/getNotificationSettings)
- [x] [setNotificationSettings](https://github.com/rizaumami/tdbot.lua/wiki/setNotificationSettings)
- [x] [resetAllNotificationSettings](https://github.com/rizaumami/tdbot.lua/wiki/resetAllNotificationSettings)
- [x] [setProfilePhoto](https://github.com/rizaumami/tdbot.lua/wiki/setProfilePhoto)
- [x] [deleteProfilePhoto](https://github.com/rizaumami/tdbot.lua/wiki/deleteProfilePhoto)
- [x] [changeName](https://github.com/rizaumami/tdbot.lua/wiki/changeName)
- [x] [changeAbout](https://github.com/rizaumami/tdbot.lua/wiki/changeAbout)
- [x] [changeUsername](https://github.com/rizaumami/tdbot.lua/wiki/changeUsername)
- [ ] [changePhoneNumber](https://github.com/rizaumami/tdbot.lua/wiki/changePhoneNumber)
- [ ] [resendChangePhoneNumberCode](https://github.com/rizaumami/tdbot.lua/wiki/resendChangePhoneNumberCode)
- [ ] [checkChangePhoneNumberCode](https://github.com/rizaumami/tdbot.lua/wiki/checkChangePhoneNumberCode)
- [x] [getActiveSessions](https://github.com/rizaumami/tdbot.lua/wiki/getActiveSessions)
- [x] [terminateSession](https://github.com/rizaumami/tdbot.lua/wiki/terminateSession)
- [x] [terminateAllOtherSessions](https://github.com/rizaumami/tdbot.lua/wiki/terminateAllOtherSessions)
- [x] [toggleGroupAdministrators](https://github.com/rizaumami/tdbot.lua/wiki/toggleGroupAdministrators)
- [x] [changeChannelUsername](https://github.com/rizaumami/tdbot.lua/wiki/changeChannelUsername)
- [x] [setChannelStickerSet](https://github.com/rizaumami/tdbot.lua/wiki/setChannelStickerSet)
- [x] [toggleChannelInvites](https://github.com/rizaumami/tdbot.lua/wiki/toggleChannelInvites)
- [x] [toggleChannelSignMessages](https://github.com/rizaumami/tdbot.lua/wiki/toggleChannelSignMessages)
- [x] [changeChannelDescription](https://github.com/rizaumami/tdbot.lua/wiki/changeChannelDescription)
- [x] [pinChannelMessage](https://github.com/rizaumami/tdbot.lua/wiki/pinChannelMessage)
- [x] [unpinChannelMessage](https://github.com/rizaumami/tdbot.lua/wiki/unpinChannelMessage)
- [x] [reportChannelSpam](https://github.com/rizaumami/tdbot.lua/wiki/reportChannelSpam)
- [x] [getChannelMembers](https://github.com/rizaumami/tdbot.lua/wiki/getChannelMembers)
- [x] [deleteChannel](https://github.com/rizaumami/tdbot.lua/wiki/deleteChannel)
- [x] [closeSecretChat](https://github.com/rizaumami/tdbot.lua/wiki/closeSecretChat)
- [x] [getChatEventLog](https://github.com/rizaumami/tdbot.lua/wiki/getChatEventLog)
- [ ] [getPaymentForm](https://github.com/rizaumami/tdbot.lua/wiki/getPaymentForm)
- [ ] [validateOrderInfo](https://github.com/rizaumami/tdbot.lua/wiki/validateOrderInfo)
- [ ] [sendPaymentForm](https://github.com/rizaumami/tdbot.lua/wiki/sendPaymentForm)
- [ ] [getPaymentReceipt](https://github.com/rizaumami/tdbot.lua/wiki/getPaymentReceipt)
- [x] [getSavedOrderInfo](https://github.com/rizaumami/tdbot.lua/wiki/getSavedOrderInfo)
- [x] [deleteSavedOrderInfo](https://github.com/rizaumami/tdbot.lua/wiki/deleteSavedOrderInfo)
- [x] [deleteSavedCredentials](https://github.com/rizaumami/tdbot.lua/wiki/deleteSavedCredentials)
- [x] [getSupportUser](https://github.com/rizaumami/tdbot.lua/wiki/getSupportUser)
- [x] [getWallpapers](https://github.com/rizaumami/tdbot.lua/wiki/getWallpapers)
- [ ] [registerDevice](https://github.com/rizaumami/tdbot.lua/wiki/registerDevice)
- [ ] [setPrivacy](https://github.com/rizaumami/tdbot.lua/wiki/setPrivacy)
- [x] [getPrivacy](https://github.com/rizaumami/tdbot.lua/wiki/getPrivacy)
- [x] [getOption](https://github.com/rizaumami/tdbot.lua/wiki/getOption)
- [x] [setOption](https://github.com/rizaumami/tdbot.lua/wiki/setOption)
- [x] [changeAccountTtl](https://github.com/rizaumami/tdbot.lua/wiki/changeAccountTtl)
- [x] [getAccountTtl](https://github.com/rizaumami/tdbot.lua/wiki/getAccountTtl)
- [x] [deleteAccount](https://github.com/rizaumami/tdbot.lua/wiki/deleteAccount)
- [x] [getChatReportSpamState](https://github.com/rizaumami/tdbot.lua/wiki/getChatReportSpamState)
- [ ] [changeChatReportSpamState](https://github.com/rizaumami/tdbot.lua/wiki/changeChatReportSpamState)
- [x] [reportChat](https://github.com/rizaumami/tdbot.lua/wiki/reportChat)
- [x] [getStorageStatistics](https://github.com/rizaumami/tdbot.lua/wiki/getStorageStatistics)
- [x] [getStorageStatisticsFast](https://github.com/rizaumami/tdbot.lua/wiki/getStorageStatisticsFast)
- [x] [optimizeStorage](https://github.com/rizaumami/tdbot.lua/wiki/optimizeStorage)
- [x] [setNetworkType](https://github.com/rizaumami/tdbot.lua/wiki/setNetworkType)
- [x] [getNetworkStatistics](https://github.com/rizaumami/tdbot.lua/wiki/getNetworkStatistics)
- [ ] [addNetworkStatistics](https://github.com/rizaumami/tdbot.lua/wiki/addNetworkStatistics)
- [x] [resetNetworkStatistics](https://github.com/rizaumami/tdbot.lua/wiki/resetNetworkStatistics)
- [ ] [setBotUpdatesStatus](https://github.com/rizaumami/tdbot.lua/wiki/setBotUpdatesStatus)
- [ ] [uploadStickerFile](https://github.com/rizaumami/tdbot.lua/wiki/uploadStickerFile)
- [ ] [createNewStickerSet](https://github.com/rizaumami/tdbot.lua/wiki/createNewStickerSet)
- [ ] [addStickerToSet](https://github.com/rizaumami/tdbot.lua/wiki/addStickerToSet)
- [ ] [setStickerPositionInSet](https://github.com/rizaumami/tdbot.lua/wiki/setStickerPositionInSet)
- [ ] [deleteStickerFromSet](https://github.com/rizaumami/tdbot.lua/wiki/deleteStickerFromSet)
- [ ] [sendCustomRequest](https://github.com/rizaumami/tdbot.lua/wiki/sendCustomRequest)
- [ ] [answerCustomQuery](https://github.com/rizaumami/tdbot.lua/wiki/answerCustomQuery)
- [x] [setAlarm](https://github.com/rizaumami/tdbot.lua/wiki/setAlarm)
- [x] [getInviteText](https://github.com/rizaumami/tdbot.lua/wiki/getInviteText)
- [x] [getTermsOfService](https://github.com/rizaumami/tdbot.lua/wiki/getTermsOfService)
- [ ] [setProxy](https://github.com/rizaumami/tdbot.lua/wiki/setProxy)
- [x] [getProxy](https://github.com/rizaumami/tdbot.lua/wiki/getProxy)
- [ ] [testCallEmpty](https://github.com/rizaumami/tdbot.lua/wiki/testCallEmpty)
- [ ] [testCallString](https://github.com/rizaumami/tdbot.lua/wiki/testCallString)
- [ ] [testCallBytes](https://github.com/rizaumami/tdbot.lua/wiki/testCallBytes)
- [ ] [testCallVectorInt](https://github.com/rizaumami/tdbot.lua/wiki/testCallVectorInt)
- [ ] [testCallVectorIntObject](https://github.com/rizaumami/tdbot.lua/wiki/testCallVectorIntObject)
- [ ] [testCallVectorString](https://github.com/rizaumami/tdbot.lua/wiki/testCallVectorString)
- [ ] [testCallVectorStringObject](https://github.com/rizaumami/tdbot.lua/wiki/testCallVectorStringObject)
- [ ] [testSquareInt](https://github.com/rizaumami/tdbot.lua/wiki/testSquareInt)
- [ ] [testNetwork](https://github.com/rizaumami/tdbot.lua/wiki/testNetwork)
- [ ] [testGetDifference](https://github.com/rizaumami/tdbot.lua/wiki/testGetDifference)
- [ ] [testUseUpdate](https://github.com/rizaumami/tdbot.lua/wiki/testUseUpdate)
- [ ] [testUseError](https://github.com/rizaumami/tdbot.lua/wiki/testUseError)
- [x] [sendText](https://github.com/rizaumami/tdbot.lua/wiki/sendText)
- [x] [sendAnimation](https://github.com/rizaumami/tdbot.lua/wiki/sendAnimation)
- [x] [sendAudio](https://github.com/rizaumami/tdbot.lua/wiki/sendAudio)
- [x] [sendDocument](https://github.com/rizaumami/tdbot.lua/wiki/sendDocument)
- [x] [sendPhoto](https://github.com/rizaumami/tdbot.lua/wiki/sendPhoto)
- [x] [sendSticker](https://github.com/rizaumami/tdbot.lua/wiki/sendSticker)
- [x] [sendVideo](https://github.com/rizaumami/tdbot.lua/wiki/sendVideo)
- [x] [sendVideoNote](https://github.com/rizaumami/tdbot.lua/wiki/sendVideoNote)
- [x] [sendVoice](https://github.com/rizaumami/tdbot.lua/wiki/sendVoice)
- [x] [sendLocation](https://github.com/rizaumami/tdbot.lua/wiki/sendLocation)
- [x] [sendVenue](https://github.com/rizaumami/tdbot.lua/wiki/sendVenue)
- [x] [sendContact](https://github.com/rizaumami/tdbot.lua/wiki/sendContact)
- [x] [sendGame](https://github.com/rizaumami/tdbot.lua/wiki/sendGame)
- [ ] [sendInvoice](https://github.com/rizaumami/tdbot.lua/wiki/sendInvoice)
- [x] [sendForwarded](https://github.com/rizaumami/tdbot.lua/wiki/sendForwarded)
