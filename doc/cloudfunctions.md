## Serverless functions in the cloud

For doing actual "work", we're going to use Google's Cloud Functions.

These are serverless workers in GCP that scale up/down as needed, are highly
fault tolerant, and don't require you to provision servers or anything of the
sort.

Now, to make this even more "extreme serverless", I'm going to make skip running
a database in GCP (CloudSQL etc) to store the guest posts. Instead, I'm
going to do the entire flow of storing via Cloud Functions --> GCS Buckets.

## Assumptions
### Managed databases are evil

This isn't actually true. I've used AWS RDS for years now in both the Postgres
and MySQL flavorings. I've also tinkered quite a bit with BigTable, as well as
Spanner, and recently AWS Aurora. Managed databases are great, in most cases.

But, using a managed database would technically be cheating, since there
are servers that I'll be provisioning, and capacity planning that I'd be doing,
so instead, we're limited to GCS.

### People are NOT evil

I'm waiting for the first troll who is going to come fill the guest book up
with profanity.

I'm waiting for the second troll who will come hammer the guest book with tons
of calls, hence triggering tons of cloud functions, hence costing me lots of
money. At least till I implement some simple rate limiting and a queue, I will
be turning off various parts of this project (but you have all the instructions
  to deploy it yourself).

### Guest book entries are not top secret

I'm not encrypting the GCS bucket. I'm not salting the guest book entries. These
are not passwords, and I'll likely be making the buckets completely public.

## Instructions
### Create a GCS bucket

This really deserves its own tutorial, so [here's](./createbucket.md) a brief
diversion.

### Deploy a Cloud Function
TODO
