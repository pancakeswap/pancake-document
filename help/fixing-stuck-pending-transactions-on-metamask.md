# Fixing Stuck Pending Transactions on MetaMask

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-MbGTDNZ6xd3_Q-qSEP5%2F-MbJqpp1p79V-5V3Lv1m%2Fdocs%20masthead%20%2812%29.png?alt=media&token=760ddc2a-1dd9-46ab-8a2f-a2ca54a29043)

If your transaction is stuck on pending in Metamask, and the “Cancel” button isn’t helping, you might need to use this method to clear your backlog.

This method works by essentially overwriting the stuck transaction with another, higher-priority transaction.

## **1. Enable Customized Transaction Nonce** <a id="1-enable-customized-transaction-nonce"></a>

1. Open your MetaMask plugin.

![](https://lh6.googleusercontent.com/fYsgD0BKjYVjrbCpbEQgMyWG_sW-4c2Ev7wu9bVzsOWtqIzCmYqiv6Xj8G_FY2TK5uYul3XaOY2WflfcW1W56R2KCuyW-Y5RjHH9DZDgUmATLlnOnMPn371nniPZqaaD7KAgYgMc)

2. Click on the colorful circle icon on the top-right and click **Settings** from the dropdown menu.

![](https://lh3.googleusercontent.com/DpSeFrHsmPNXU73C3NB9iRANEe81rJ2XUhbxs6k7PqJSVy6IkAijeX_TeIbUupalmD3mlE2G0C90XHJJy_JPk-_mswNRf4liUwR4AUhx2AWygp4yIP9kjHo1QQk_60wEtjGkfwSk)

3. In the Settings menu, select **Advanced**.

![](https://lh4.googleusercontent.com/F-o1qfi84wh6YNUP16b8lbyS6f8i04SYEUR2VrncMbBaoeaAjOw4Af_oOwRUfWnhZn6NFb4O1uopoc1KNego8XelHmDDWeRRAb0oMJGE_ZI_xJJeqfH-bJrai0pakyxC-235E4nq)

4. Scroll down until you see **Advanced gas controls**. Toggle this to ON.

![](https://lh5.googleusercontent.com/ePraz_2Z8k1V62DMROjv0jbIjEcf8ATvaH-Lxe5wtoNo6oVTyRPelC1m7UVaizcNpW5bHByrbC9xv1KDZfjNnXvQ8J0ukHUHK7vK4rX5gpQVHmfyJr81wCGdeArvksNhshon1Btn)

5. Still in Advanced settings, keep scrolling until you see **Customize transaction nonce**. Toggle this to ON.

## **2. Find Your Stuck Transaction** <a id="2-find-your-stuck-transaction"></a>

We’re now going to find the transaction that’s stuck, and make a note of the “nonce”. That’s a kind of identifier, which we’ll re-use later.

![](https://lh4.googleusercontent.com/xKBEnt5a62c5Wzg_MCLIbVUWuL4fws1ohBAX9LAkGS71vslHk7QuMF24jAfkAdmsLunPVfT9c3FxCmGar5z7jNZnd4WMgzQsoxxbYw1Lp59Az5kG72COn0JblFXktHbmgMnF1LeY)

6. Go back to the top page of MetaMask. In the “Assets” tab, find the token type of your stuck transaction \(in this case, CAKE\).

![](https://lh5.googleusercontent.com/9qVjhK1kEKDL8l4TTdOFo4o547PDIIeQpCCY18gPyaUFJrpFbyYhMfBQ1CRzjjrllgrcqVbwkhxKCZBNlIad8J1yCpMVhsBKjIAcwfsQHQb7jnl2RD2ufQU-zNEn2Hn2g4LGvYDU)

6. In the token’s menu, find your **Pending** transaction in the Queue area. Click on your transaction for more details.

![](https://lh4.googleusercontent.com/HMd5iKjIvm-f7Xi7xtecTsq56x1i15GjUkwCm5Z_83xMfOXDd2jabcCDyUwELf51IHseEeCk2WnvWfHwTSUlFnLAJrmjkkOfm_fA5fimgdABnYfdjmBxxst8TOaUJUhc2iO_CN-k)

7. Look for the **Nonce** entry, and take note of this number.

## **3. Overwrite the Stuck Transaction** <a id="3-overwrite-the-stuck-transaction"></a>

Now we’re going to make a new transaction to replace the stuck one. We’ll customize the Nonce number, so that it’s the same as the one that you just wrote down.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M_Qf9PqrqKwKENMLChq%2F-M_QfJwbI-p6skTud7_o%2Fimage.png?alt=media&token=13db2345-9ad7-46a4-9937-7f26d7187749)

8. Create a new transaction to replace your stuck transaction. This time around, increase the **Transaction Fee**. Here we’ve increased it from 9 to 20. This will make it more likely for your transaction to be added to a block.

![](https://gblobscdn.gitbook.com/assets%2F-MHREX7DHcljbY5IkjgJ%2F-M_Qf9PqrqKwKENMLChq%2F-M_Qft-wFWL0NENZfvV_%2Fimage.png?alt=media&token=14028feb-3c51-405c-bc3e-3d8e87d1d37d)

9. On the confirmation page, make sure your Gas Price is now at your new, higher amount.

10. Find the **CUSTOM NONCE** entry and change the nonce to the number you wrote down in step 7. Now click Confirm.

![](https://lh6.googleusercontent.com/PYhYm2ro0SVzerBo5qguFIPOYl0DjLSfl0JT8UdfN3T4i-0hjBq-CQvr-UA0bSyG-ZndrWmLGptfZUcnGBlvUk118GGZn7ciDNaC4hmfovH9v_M5XMIYmkAmB-Fr-6TTpYnnDX1p)

11. Your new transaction should now be accepted into a block. To check, open MetaMask and click the **Activity** tab.

![](https://lh6.googleusercontent.com/Iw3e0YP4ORhPgw8-MNxvzlDlfgG5nD226P4ixiziPC_9j3_LfU3o1-_LA2yDmegbRw5x9Sgk3RACFJJkyJDrFJA1j2J93H21uGhhWabkdDQUHsU_oVdkZVQTTWaQPzXHAWClpsb4)

12. Your completed transaction should show at the top of your Activity list. If it still says “Pending” in orange you’ll need to wait a little longer, or try the process again with an even higher transaction fee \(gas price\).

Since no wallet can create two transactions of the same nonce, if the replacement transaction you make is successful, your stuck transaction will be canceled.

