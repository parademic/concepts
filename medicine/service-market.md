## Prerequisites

Today, the work of a doctor is a job in any medical center or hospital, where he receives patients, prescribes examinations, prescribes treatment, etc. He also receives a salary there, which in some countries can be quite low.

Patients, in turn, can often only receive treatment from the doctors available in their urban or rural hospitals. If any difficult case arises, then ordinary doctors often have no idea how to deal with it, and send the patient to a more serious institution, or try to prescribe a treatment on their own, which could potentially be wrong.

## The following problems result

- a doctor cannot earn as much as he wants from his work
- if a doctor can solve complex cases, then they may simply not come across to him in a regular hospital
- a patient with a complex case cannot receive qualified treatment so easily
- doctors and patients are separated by countries, they cannot work together if they are not in the same city or at least the country

## Suggested solution

A large-scale network that can connect doctors and patients around the world.

## Solution design
### First solution
The first implementation is a blockchain system.

#### Current schema

1. A person has a health problem.
2. He makes an appointment with the doctor.
3. A consultation is being held.
4. The patient receives a treatment regimen or appointments for examinations.
5. Consultation is paid - the patient transfers money to the company where the doctor works.
6. Part of the funds is received by the company, part - by the specialist himself.

#### Proposed scheme

1. A person has a health problem.
2. He sends a transaction to the blockchain with a description of his problem and the amount he is willing to pay for its solution, and various parameters that briefly describe the problem. (the reward for solving the problem is taken from the patient's account)
3. The specialist indexes the blockchain and sees the posted problems and the rewards for solving them. It can search for various parameters that describe the problem.
4. The specialist chooses the problem he wants to solve and the reward for which he is satisfied.
5. A transaction is sent to the blockchain that a certain wallet has captured the solution to a certain problem.
6. The patient looks at information about the specialist, which is provided in the form of NFT and transactions with comments on his wallet, which he cannot delete.
7. If the patient is satisfied with the specialist, he sends a transaction confirming the capture of the problem by the doctor.
8. The specialist studies the problem and, if necessary, sends transactions to obtain additional information (examinations, anamnesis, etc.)
9. The patient provides the necessary information.
10. If the specialist has enough information to prescribe the treatment, he sends a transaction containing the treatment.
11. The work of validators begins. Validators are network members who receive a reward for approving or denying a treatment (they must explain their choice in a comment to the transaction).
12. After all the conditions are met by the validators, the patient receives a summary of who voted for what with comments on the selected decision (you can see the decision of each validator and comment)
13. If the patient is satisfied with the summary of validators, then he approves the treatment. The treatment goes to the user, and the reward goes to the specialist.

#### Peculiarities

- the patient can cancel his application at any time if it has not been captured by a specialist and approved by the patient
- if the application is approved, but the patient wants to cancel it, then the specialist sends the treatment in the form in which it was ready at the time of the cancellation of the application and the amount that he wants to receive for it (part of the full reward for the treatment). Validators consider this situation and either approve such a deal and the doctor receives a part of the full reward, or reject it and it goes back to the specialist. This happens until the doctor indicates the amount for partial treatment and manipulations with the patient, which is approved by the validators. After that, part of the reward will go to the specialist, part will return to the patient, and the validators will receive tokens. (that is, the validators also have an interest in closing the transaction)
- validators are network nodes that act as a supervisory authority, ensuring the correctness of treatment and doctor-patient interaction by voting
- the specialist can respond to the application by demanding an increase in the reward. The patient considers this answer - studies the specialist's wallet, his achievements in the form of NFT. The patient can agree to this deal, and increase the reward. Then this application will be automatically captured by this specialist.
- after the patient undergoes treatment, he can reward the specialist with donations containing feedback in the comments
- the cost of tokens received by validators must be maintained at the required level
- patients are depersonalized and presented in the form of ordinary wallets
- doctors are not anonymized - their wallets contain transactions with full name, description of their activities
- institutes and medical institutions can issue to NFT doctors about the completion of training or the temporary period of the place of work and position
- the doctor must have an NFT license for medical practice, which can be issued by any accredited supervisory body (and can also revoke this NFT)
- validators should be divided into groups - doctors, scientists, PhDs, researchers, ordinary people (?), etc. Each title must be confirmed by the corresponding NFT (except ordinary people?). After validation, the user receives a summary of how many and from which group of validators voted FOR and AGAINST and decides to approve the treatment. If the user does not approve the treatment for a long time (how long?), the reward is transferred to the doctor, and the treatment is transferred to the user.
- the patient can study the profile of who wants to capture his application (see NFT and transactions) and make a decision on the basis of this to approve the capture
- the doctor must confirm with the help of an electronic signature that he is he, then he has the opportunity to issue electronic prescriptions that are attached to the treatment transaction. These prescriptions can be viewed by a pharmacist and send a transaction about the release of the drug, the doctor receives a notification about this after indexing the blockchain. If the amount of the drug has reached the limit set by the doctor, the prescription becomes invalid.

#### Questions

- how to prevent an abuse by the validators, in the form of an intentional closing of the transaction as quickly as possible?
- if the reward in the form of tokens increases for each validation, then how to prevent the abuse in the form of an intentional rejection of the doctor's application to increase their number?
- the use of NFTs issued by accredited institutions that confirm the qualifications of a specialist looks quite convenient. Should we use DID instead?
- the resulting system in the form of a blockchain allows various researchers to collect data on various variations of diseases. However, this interaction can be rather slow. It is possible to carry out all interaction on a centralized service, but then it can control all interaction and be not entirely honest, and information stored in a centralized service may be lost. Which option to choose?
- сan users find just similar cases so they don't have to pay doctors to treat their case?
- if you deploy your own blockchain, then how to maintain the coin used in it at a certain value? Is it necessary to create a bridge to existing blockchains?
