all: person.pb.cc test_person test_json

person.pb.cc person.pb.h:person.proto
	protoc --cpp_out=./ person.proto

test_person: test_person.cpp person.pb.cc person.pb.h
	${CXX} -g -o test_person test_person.cpp person.pb.cc -lprotobuf -lpthread

test_json: test_json.cpp person.pb.cc person.pb.h ../libpb2json.a
	${CXX} -g -o test_json test_json.cpp person.pb.cc ../libpb2json.a  -I../  -lprotobuf -ljansson -lpthread

clean:
	rm -f test_person test_json person.pb.cc person.pb.h dump
