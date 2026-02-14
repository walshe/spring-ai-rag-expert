# Spring AI RAG Expert


    ❯ curl -X POST http://localhost:8080/ask \
         -H "Content-Type: application/json" \
         -d '{"question": "What is a good truck to pull a Sportsman 212 boat?"}'

        {"answer":"The Sportsman Open 212 boat has a tested weight of 3,458 lbs. To find a suitable truck to tow this boat, we need to ensure that the truck's towing capacity is greater than or equal to the boat's weight.\n\nLooking at the available trucks:\n- Chevy Traverse can tow up to 5,000 lbs and costs $43,000.\n- Chevy Colorado can tow up to 7,000 lbs and costs $55,000.\n- Chevy 1500 can tow up to 9,100 lbs and costs $65,000.\n- Chevy 2500 can tow up to 14,500 lbs and costs $75,000.\n- Chevy 3500 can tow up to 18,500 lbs and costs $80,000.\n- Chevy 3500 Duramax can tow up to 36,000 lbs and costs $90,000.\n\nThe cheapest truck that can adequately tow the Sportsman Open 212 boat is the Chevy Traverse, which costs $43,000 and has a towing capacity of 5,000 lbs, which is sufficient for the boat's tested weight of 3,458 lbs."}%     




    - RAG
    - openai
    - milvus vector store
    - etcd (Metastore):
        Purpose: It stores metadata for the Milvus cluster.
        Role: It keeps track of the system state, collection schemas, and data location information.
        Configuration: You can see Milvus is linked to it via the ETCD_ENDPOINTS: etcd:2379 environment variable (line 46).
    
    - MinIO (Object Storage):
        Purpose: It serves as the primary data storage layer for Milvus.
        Role: Milvus uses it to store large-scale data, including vector data, index files, and transaction logs (WAL).
        Configuration: Milvus connects to it using the MINIO_ADDRESS: minio:9000 environment variable (line 47).