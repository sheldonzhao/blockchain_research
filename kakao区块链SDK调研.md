## 1. dependency
```
<dependency>
<groupId>com.klaytn.caver</groupId>
<artifactId>core</artifactId>
<version>1.0.0</version>
</dependency>
```

## 2. create wallet

```java
public static void createWallet() {
try {
KlayWalletUtils.generateNewWalletFile("1", new File("./"));
} catch (Exception e) {
System.out.println(e);
}
}
```

## 3. transfer

```java
public static void transfer() {
Caver caver = Caver.build("https://api.baobab.klaytn.net:8651");
KlayCredentials credentials;

try {
credentials = KlayWalletUtils.loadCredentials("1", "./wallet.json");
System.out.println(credentials.getAddress());
TransactionManager transactionManager;
transactionManager = new TransactionManager.Builder(caver, credentials)
.setChaindId(ChainId.BAOBAB_TESTNET).build();

ValueTransferTransaction valueTransferTransaction = ValueTransferTransaction.create(
credentials.getAddress(),  // fromAddress
"0xe97f27e9a5765ce36a7b919b1cb6004c7209217e",  // toAddress
BigInteger.ONE,  // value
BigInteger.valueOf(100_000)  // gasLimit
);

KlayRawTransaction klayRawTransaction = transactionManager.sign(valueTransferTransaction);

try {
String transactionHash = transactionManager.send(klayRawTransaction);
TransactionReceiptProcessor transactionReceiptProcessor = new PollingTransactionReceiptProcessor(caver, 1000, 15);  // pollingSleepDuration = 1000, pollingAttempts = 15
try {
KlayTransactionReceipt.TransactionReceipt transactionReceipt = transactionReceiptProcessor.waitForTransactionReceipt(transactionHash);
System.out.println(transactionReceipt.getBlockNumber());
System.out.println(transactionReceipt.getTransactionHash());
} catch (TransactionException e) {
System.out.println("transaction exception:" + e);
}
} catch (IOException e) {
System.out.println("io exception:" + e);
} catch (PlatformErrorException e) {
System.out.println("platform error exception:" + e);
}

} catch (Exception e) {
System.out.println(e);
}

}
```
